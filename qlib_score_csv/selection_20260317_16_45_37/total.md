# params 
 {'predict_dates': [{'start': '2026-03-17', 'end': '2026-03-17'}], 'provider_uri': '~/.qlib/qlib_data/cn_data/', 'uri_folder': '~/.qlibAssistant/mlruns/', 'analysis_folder': '~/.qlibAssistant/analysis/', 'pfx_name': 'p', 'sfx_name': 's', 'model_name': 'Linear', 'dataset_name': 'Alpha158', 'stock_pool': 'csi300', 'step': 60, 'rolling_type': 'expanding', 'model_filter': ['.*'], 'rec_filter': [{'ic': 0.02}, {'icir': 0.25}, {'rankic': 0.02}, {'rankicir': 0.2}]}



 # model info 

Experiment: EXP_DEnsembleModel_Alpha158_csi300_custom_step0_s_20260317_14 973449107619060661 (Recorders: 2/5)

	Recorder: bf42b3855daa41b1819fa3080e2e9b70

		Model: {'id': 'bf42b3855daa41b1819fa3080e2e9b70', 'model': 'DEnsembleModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.029, 'ICIR': 0.279, 'Rank IC': 0.033, 'Rank ICIR': 0.315}, 'data_train_vec': ['2024-03-17', '2025-09-16'], 'train_time_vec': ['2026-03-17', '2026-03-17']}

	Recorder: d11602f48a804f6f89179d055f99c57b

		Model: {'id': 'd11602f48a804f6f89179d055f99c57b', 'model': 'DEnsembleModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.036, 'ICIR': 0.311, 'Rank IC': 0.067, 'Rank ICIR': 0.635}, 'data_train_vec': ['2025-03-17', '2025-12-16'], 'train_time_vec': ['2026-03-17', '2026-03-17']}
