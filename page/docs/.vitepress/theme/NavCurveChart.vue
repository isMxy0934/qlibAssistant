<template>
  <div>
    <div class="kpi-bar">
      <div v-for="item in kpiItems" :key="item.label" class="kpi-card">
        <div class="kpi-label">{{ item.label }}</div>
        <div class="kpi-value">{{ item.value }}</div>
      </div>
    </div>
    <div ref="hostEl" class="chart-host"></div>
    <p class="chart-status">{{ statusText }}</p>
    <div class="legend">
      <span class="legend-item">
        <i class="legend-dot strategy"></i>
        策略净值
      </span>
      <span class="legend-item">
        <i class="legend-dot benchmark"></i>
        CSI300净值
      </span>
    </div>
  </div>
</template>

<script setup>
import { onMounted, ref } from "vue";
import { createChart, LineSeries, AreaSeries, CrosshairMode } from "lightweight-charts";

const hostEl = ref(null);
const statusText = ref("");
const kpiItems = ref([
  { label: "策略累计", value: "--" },
  { label: "基准累计", value: "--" },
  { label: "超额累计", value: "--" },
  { label: "策略年化", value: "--" },
  { label: "最大回撤", value: "--" },
  { label: "日胜率", value: "--" },
]);

function normalizeData(rawRows) {
  if (!Array.isArray(rawRows)) return { strategy: [], benchmark: [] };

  const strategy = [];
  const benchmark = [];

  for (const row of rawRows) {
    const rawTime = row.date || row.time;
    const d = rawTime ? new Date(rawTime) : null;
    const time = d && Number.isFinite(d.getTime()) ? Math.floor(d.getTime() / 1000) : null;
    const strategyValue = Number(
      row.strategy_equity ?? row.strategy_nav ?? row.strategy
    );
    const benchmarkValue = Number(
      row.csi300_equity ?? row.benchmark_nav ?? row.csi300
    );

    if (time && Number.isFinite(strategyValue)) {
      strategy.push({ time, value: strategyValue });
    }
    if (time && Number.isFinite(benchmarkValue)) {
      benchmark.push({ time, value: benchmarkValue });
    }
  }

  return { strategy, benchmark };
}

function resolveDataUrls() {
  const base = (import.meta.env.BASE_URL || "/").replace(/\/+$/, "");
  return [
    `${base}/data/mahoupao_nav_curve.json`,
    "/data/mahoupao_nav_curve.json",
  ];
}

function fmtPct(x) {
  return Number.isFinite(x) ? `${(x * 100).toFixed(2)}%` : "--";
}

function calcDrawdown(strategySeries) {
  let maxVal = -Infinity;
  const drawdown = [];
  for (const p of strategySeries) {
    if (p.value > maxVal) maxVal = p.value;
    const dd = maxVal > 0 ? p.value / maxVal - 1 : 0;
    drawdown.push({ time: p.time, value: dd });
  }
  return drawdown;
}

function calcKpis(strategy, benchmark, drawdown) {
  if (!strategy.length) return;
  const s0 = strategy[0].value;
  const sN = strategy[strategy.length - 1].value;
  const b0 = benchmark.length ? benchmark[0].value : NaN;
  const bN = benchmark.length ? benchmark[benchmark.length - 1].value : NaN;
  const n = strategy.length;

  const strategyCum = sN / s0 - 1;
  const benchmarkCum = Number.isFinite(b0) && Number.isFinite(bN) ? bN / b0 - 1 : NaN;
  const excessCum = Number.isFinite(benchmarkCum) ? strategyCum - benchmarkCum : NaN;
  const strategyAnn = n > 1 ? Math.pow(sN / s0, 252 / (n - 1)) - 1 : NaN;
  const maxDd = drawdown.length ? Math.min(...drawdown.map((d) => d.value)) : NaN;

  let win = 0;
  let total = 0;
  if (benchmark.length && benchmark.length === strategy.length) {
    for (let i = 1; i < strategy.length; i += 1) {
      const sr = strategy[i].value / strategy[i - 1].value - 1;
      const br = benchmark[i].value / benchmark[i - 1].value - 1;
      if (Number.isFinite(sr) && Number.isFinite(br)) {
        total += 1;
        if (sr > br) win += 1;
      }
    }
  }
  const winRate = total > 0 ? win / total : NaN;

  kpiItems.value = [
    { label: "策略累计", value: fmtPct(strategyCum) },
    { label: "基准累计", value: fmtPct(benchmarkCum) },
    { label: "超额累计", value: fmtPct(excessCum) },
    { label: "策略年化", value: fmtPct(strategyAnn) },
    { label: "最大回撤", value: fmtPct(maxDd) },
    { label: "日胜率", value: fmtPct(winRate) },
  ];
}

onMounted(async () => {
  if (!hostEl.value) return;

  const shadowRoot = hostEl.value.attachShadow({ mode: "open" });
  const styleEl = document.createElement("style");
  styleEl.textContent = `
    .chart-main-wrap {
      position: relative;
      height: 430px;
      width: 100%;
      border: 1px solid #e2e8f0;
      border-radius: 8px 8px 0 0;
      overflow: hidden;
      background: #ffffff;
    }
    .chart-dd-wrap {
      position: relative;
      height: 140px;
      width: 100%;
      border: 1px solid #e2e8f0;
      border-top: 0;
      border-radius: 0 0 8px 8px;
      overflow: hidden;
      background: #ffffff;
    }
    .overlay {
      position: absolute;
      top: 10px;
      left: 10px;
      z-index: 10;
      min-width: 250px;
      padding: 8px 10px;
      border-radius: 6px;
      border: 1px solid #dbe5f1;
      background: rgba(255, 255, 255, 0.92);
      backdrop-filter: blur(2px);
      color: #334155;
      font-size: 12px;
      line-height: 1.5;
      box-shadow: 0 1px 4px rgba(15, 23, 42, 0.08);
      pointer-events: none;
    }
    .overlay .date {
      font-weight: 600;
      margin-bottom: 2px;
      color: #0f172a;
    }
    .overlay .row {
      display: flex;
      justify-content: space-between;
      gap: 12px;
      white-space: nowrap;
    }
    .overlay .k {
      color: #64748b;
    }
    .overlay .v.strategy {
      color: #2563eb;
      font-weight: 600;
    }
    .overlay .v.benchmark {
      color: #ef4444;
      font-weight: 600;
    }
    .overlay .v.excess {
      color: #0f172a;
      font-weight: 600;
    }
    .overlay .v.drawdown {
      color: #334155;
      font-weight: 600;
    }
  `;
  const chartMainWrap = document.createElement("div");
  chartMainWrap.className = "chart-main-wrap";
  const chartDdWrap = document.createElement("div");
  chartDdWrap.className = "chart-dd-wrap";
  const overlay = document.createElement("div");
  overlay.className = "overlay";
  overlay.innerHTML = `
    <div class="date">--</div>
    <div class="row"><span class="k">策略净值</span><span class="v strategy">--</span></div>
    <div class="row"><span class="k">CSI300净值</span><span class="v benchmark">--</span></div>
    <div class="row"><span class="k">超额(策略-基准)</span><span class="v excess">--</span></div>
    <div class="row"><span class="k">回撤</span><span class="v drawdown">--</span></div>
  `;
  shadowRoot.appendChild(styleEl);
  shadowRoot.appendChild(chartMainWrap);
  shadowRoot.appendChild(chartDdWrap);
  chartMainWrap.appendChild(overlay);

  const mainChart = createChart(chartMainWrap, {
    width: hostEl.value.clientWidth,
    height: 430,
    layout: {
      background: { color: "#ffffff" },
      textColor: "#334155",
    },
    localization: {
      locale: "zh-CN",
      dateFormat: "yyyy-MM-dd",
    },
    grid: {
      vertLines: { color: "#eef2f7" },
      horzLines: { color: "#eef2f7" },
    },
    rightPriceScale: { borderColor: "#e2e8f0" },
    timeScale: {
      visible: false,
      borderColor: "#e2e8f0",
      timeVisible: false,
      secondsVisible: false,
      barSpacing: 12,
      rightOffset: 2,
      fixLeftEdge: true,
      fixRightEdge: true,
    },
    crosshair: { mode: CrosshairMode.Normal },
  });

  const ddChart = createChart(chartDdWrap, {
    width: hostEl.value.clientWidth,
    height: 140,
    layout: {
      background: { color: "#ffffff" },
      textColor: "#334155",
    },
    grid: {
      vertLines: { color: "#eef2f7" },
      horzLines: { color: "#eef2f7" },
    },
    rightPriceScale: {
      borderColor: "#e2e8f0",
      scaleMargins: { top: 0.15, bottom: 0.12 },
    },
    timeScale: {
      visible: true,
      borderColor: "#e2e8f0",
      timeVisible: true,
      secondsVisible: false,
      barSpacing: 12,
      rightOffset: 2,
      fixLeftEdge: true,
      fixRightEdge: true,
    },
    localization: {
      locale: "zh-CN",
      dateFormat: "yyyy-MM-dd",
    },
    crosshair: { mode: CrosshairMode.Normal },
  });

  const strategySeries = mainChart.addSeries(LineSeries, {
    title: "Strategy",
    color: "#2563eb",
    lineWidth: 2,
  });

  const benchmarkSeries = mainChart.addSeries(LineSeries, {
    title: "CSI300",
    color: "#ef4444",
    lineWidth: 2,
  });

  const drawdownSeries = ddChart.addSeries(AreaSeries, {
    title: "Drawdown",
    lineColor: "#475569",
    topColor: "rgba(71, 85, 105, 0.35)",
    bottomColor: "rgba(71, 85, 105, 0.05)",
    lineWidth: 1,
    priceFormat: { type: "price", precision: 2, minMove: 0.01 },
  });

  let strategyMap = new Map();
  let benchmarkMap = new Map();
  let drawdownMap = new Map();

  const formatDate = (time) => {
    if (typeof time === "number") {
      const d = new Date(time * 1000);
      const yyyy = d.getFullYear();
      const mm = String(d.getMonth() + 1).padStart(2, "0");
      const dd = String(d.getDate()).padStart(2, "0");
      return `${yyyy}-${mm}-${dd}`;
    }
    if (time && typeof time === "object" && "year" in time) {
      const mm = String(time.month).padStart(2, "0");
      const dd = String(time.day).padStart(2, "0");
      return `${time.year}-${mm}-${dd}`;
    }
    return "--";
  };

  const updateOverlay = (dateStr, strategyVal, benchmarkVal, drawdownVal) => {
    const strategyText = Number.isFinite(strategyVal) ? strategyVal.toFixed(4) : "--";
    const benchmarkText = Number.isFinite(benchmarkVal) ? benchmarkVal.toFixed(4) : "--";
    const excess = Number.isFinite(strategyVal) && Number.isFinite(benchmarkVal)
      ? (strategyVal - benchmarkVal).toFixed(4)
      : "--";
    const drawdownText = Number.isFinite(drawdownVal) ? `${(drawdownVal * 100).toFixed(2)}%` : "--";

    overlay.innerHTML = `
      <div class="date">${dateStr}</div>
      <div class="row"><span class="k">策略净值</span><span class="v strategy">${strategyText}</span></div>
      <div class="row"><span class="k">CSI300净值</span><span class="v benchmark">${benchmarkText}</span></div>
      <div class="row"><span class="k">超额(策略-基准)</span><span class="v excess">${excess}</span></div>
      <div class="row"><span class="k">回撤</span><span class="v drawdown">${drawdownText}</span></div>
    `;
  };

  try {
    let data = null;
    for (const url of resolveDataUrls()) {
      const res = await fetch(url);
      if (res.ok) {
        data = await res.json();
        break;
      }
    }
    if (!data) {
      throw new Error("无法读取净值数据文件");
    }

    const { strategy, benchmark } = normalizeData(data);
    if (!strategy.length && !benchmark.length) {
      throw new Error("数据为空或字段名不匹配");
    }

    strategySeries.setData(strategy);
    benchmarkSeries.setData(benchmark);
    const drawdown = calcDrawdown(strategy);
    drawdownSeries.setData(drawdown.map((d) => ({ time: d.time, value: d.value * 100 })));
    calcKpis(strategy, benchmark, drawdown);
    strategyMap = new Map(strategy.map((d) => [d.time, d.value]));
    benchmarkMap = new Map(benchmark.map((d) => [d.time, d.value]));
    drawdownMap = new Map(drawdown.map((d) => [d.time, d.value]));
    mainChart.timeScale().fitContent();
    ddChart.timeScale().fitContent();
    const lastTime = strategy.length
      ? strategy[strategy.length - 1].time
      : benchmark[benchmark.length - 1].time;
    updateOverlay(
      formatDate(lastTime),
      strategyMap.get(lastTime),
      benchmarkMap.get(lastTime),
      drawdownMap.get(lastTime)
    );
    statusText.value = `加载成功：${Math.max(strategy.length, benchmark.length)} 个交易日`;
  } catch (err) {
    console.error("加载净值数据失败:", err);
    statusText.value = `加载失败：${String(err)}`;
  }

  const syncFromTime = (time) => {
    const dateStr = formatDate(time);
    const strategyVal = typeof time === "number" ? strategyMap.get(time) : null;
    const benchmarkVal = typeof time === "number" ? benchmarkMap.get(time) : null;
    const drawdownVal = typeof time === "number" ? drawdownMap.get(time) : null;
    updateOverlay(dateStr, strategyVal, benchmarkVal, drawdownVal);
  };

  mainChart.subscribeCrosshairMove((param) => {
    if (!param || !param.time) return;
    const strategyPoint = param.seriesData.get(strategySeries);
    const benchmarkPoint = param.seriesData.get(benchmarkSeries);
    const strategyVal = strategyPoint && "value" in strategyPoint ? strategyPoint.value : strategyMap.get(param.time);
    const benchmarkVal = benchmarkPoint && "value" in benchmarkPoint ? benchmarkPoint.value : benchmarkMap.get(param.time);
    updateOverlay(formatDate(param.time), strategyVal, benchmarkVal, drawdownMap.get(param.time));
  });

  ddChart.subscribeCrosshairMove((param) => {
    if (!param || !param.time) return;
    syncFromTime(param.time);
  });

  let syncing = false;
  mainChart.timeScale().subscribeVisibleLogicalRangeChange((range) => {
    if (syncing || !range) return;
    syncing = true;
    ddChart.timeScale().setVisibleLogicalRange(range);
    syncing = false;
  });
  ddChart.timeScale().subscribeVisibleLogicalRangeChange((range) => {
    if (syncing || !range) return;
    syncing = true;
    mainChart.timeScale().setVisibleLogicalRange(range);
    syncing = false;
  });

  window.addEventListener("resize", () => {
    if (hostEl.value) {
      mainChart.resize(hostEl.value.clientWidth, 430);
      ddChart.resize(hostEl.value.clientWidth, 140);
    }
  });
});
</script>

<style scoped>
.kpi-bar {
  display: grid;
  grid-template-columns: repeat(6, minmax(120px, 1fr));
  gap: 10px;
  margin-bottom: 12px;
}

.kpi-card {
  border: 1px solid var(--vp-c-divider);
  border-radius: 8px;
  padding: 8px 10px;
  background: var(--vp-c-bg-soft);
}

.kpi-label {
  font-size: 12px;
  color: var(--vp-c-text-2);
}

.kpi-value {
  margin-top: 2px;
  font-size: 15px;
  font-weight: 700;
  color: var(--vp-c-text-1);
}

.chart-host {
  width: 100%;
}

.chart-status {
  margin-top: 8px;
  color: var(--vp-c-text-2);
  font-size: 13px;
}

.legend {
  display: flex;
  gap: 16px;
  align-items: center;
  margin-top: 8px;
  font-size: 13px;
  color: var(--vp-c-text-2);
}

.legend-item {
  display: inline-flex;
  align-items: center;
  gap: 6px;
}

.legend-dot {
  display: inline-block;
  width: 10px;
  height: 10px;
  border-radius: 999px;
}

.legend-dot.strategy {
  background: #2563eb;
}

.legend-dot.benchmark {
  background: #ef4444;
}
</style>
