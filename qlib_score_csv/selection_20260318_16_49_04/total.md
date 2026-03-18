# params 
 {'predict_dates': [{'start': '2026-03-18', 'end': '2026-03-18'}], 'provider_uri': '~/.qlib/qlib_data/cn_data/', 'uri_folder': '~/.qlibAssistant/mlruns/', 'analysis_folder': '~/.qlibAssistant/analysis/', 'pfx_name': 'p', 'sfx_name': 's', 'model_name': 'Linear', 'dataset_name': 'Alpha158', 'stock_pool': 'csi300', 'step': 60, 'rolling_type': 'expanding', 'model_filter': ['.*'], 'rec_filter': [{'ic': 0.02}, {'icir': 0.25}, {'rankic': 0.02}, {'rankicir': 0.2}]}



 # model info 

Experiment: EXP_LGBModel_Alpha158_csi300_custom_step0_s_20260318_16 239905609264785716 (Recorders: 1/5)

	Recorder: 7a2506f3fb6240adbcc8ca66715f8c1a

		Model: {'id': '7a2506f3fb6240adbcc8ca66715f8c1a', 'model': 'LGBModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.029, 'ICIR': 0.262, 'Rank IC': 0.046, 'Rank ICIR': 0.346}, 'data_train_vec': ['2024-03-18', '2025-09-17'], 'train_time_vec': ['2026-03-18', '2026-03-18']}
Experiment: EXP_DEnsembleModel_Alpha158_csi300_custom_step0_s_20260318_14 195790341437545230 (Recorders: 1/5)

	Recorder: 0bb9c48764304c478be13c13a40122e8

		Model: {'id': '0bb9c48764304c478be13c13a40122e8', 'model': 'DEnsembleModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.027, 'ICIR': 0.272, 'Rank IC': 0.037, 'Rank ICIR': 0.337}, 'data_train_vec': ['2024-03-18', '2025-09-17'], 'train_time_vec': ['2026-03-18', '2026-03-18']}
Experiment: EXP_LinearModel_Alpha158_csi300_custom_step0_s_20260318_13 798417721556234529 (Recorders: 1/5)

	Recorder: e67fc040e5f2418599eac5d7c923321d

		Model: {'id': 'e67fc040e5f2418599eac5d7c923321d', 'model': 'LinearModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.031, 'ICIR': 0.322, 'Rank IC': 0.045, 'Rank ICIR': 0.452}, 'data_train_vec': ['2025-03-18', '2025-12-17'], 'train_time_vec': ['2026-03-18', '2026-03-18']}
Experiment: EXP_XGBModel_Alpha158_csi300_custom_step0_s_20260318_13 238419595466424957 (Recorders: 1/5)

	Recorder: 1dcc905ff30240789f7e30b60ed5e48d

		Model: {'id': '1dcc905ff30240789f7e30b60ed5e48d', 'model': 'XGBModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.032, 'ICIR': 0.315, 'Rank IC': 0.054, 'Rank ICIR': 0.502}, 'data_train_vec': ['2025-03-18', '2025-12-17'], 'train_time_vec': ['2026-03-18', '2026-03-18']}
