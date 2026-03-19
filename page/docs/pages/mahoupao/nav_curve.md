# 净值曲线（Lightweight Charts）

该页面使用 `Lightweight Charts` 绘制策略与 CSI300 的净值变化曲线。  
默认读取 `/data/mahoupao_nav_curve.json`，你只需要更新这个 JSON 文件即可自动刷新图表。

<NavCurveChart />

## 数据格式

`/data/mahoupao_nav_curve.json` 示例：

```json
[
  { "date": "2026-03-10", "strategy_equity": 1.0010, "csi300_equity": 1.0003 },
  { "date": "2026-03-11", "strategy_equity": 1.0042, "csi300_equity": 1.0016 },
  { "date": "2026-03-12", "strategy_equity": 1.0037, "csi300_equity": 1.0021 }
]
```

