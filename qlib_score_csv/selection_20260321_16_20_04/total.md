# params 
 {'predict_dates': [{'start': '2026-03-20', 'end': '2026-03-20'}], 'provider_uri': '~/.qlib/qlib_data/cn_data/', 'uri_folder': '~/.qlibAssistant/mlruns/', 'analysis_folder': '~/.qlibAssistant/analysis/', 'pfx_name': 'p', 'sfx_name': 's', 'model_name': 'Linear', 'dataset_name': 'Alpha158', 'stock_pool': 'csi300', 'step': 60, 'rolling_type': 'expanding', 'model_filter': ['.*'], 'rec_filter': [{'ic': 0.001}, {'icir': 0.001}, {'rankic': 0.001}, {'rankicir': 0.001}]}



 # model info 

Experiment: EXP_CatBoostModel_Alpha158_csi300_custom_step0_s_20260321_15 378345063001606225 (Recorders: 1/5)

	Recorder: 9baf1fb738264c528c80fc34061ba37d

		Model: {'id': '9baf1fb738264c528c80fc34061ba37d', 'model': 'CatBoostModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.016, 'ICIR': 0.138, 'Rank IC': 0.028, 'Rank ICIR': 0.222}, 'data_train_vec': ['2025-03-21', '2025-12-20'], 'train_time_vec': ['2026-03-21', '2026-03-21'], 'rank_icir': '0.222', 'weight': '0.055'}
Experiment: EXP_LGBModel_Alpha158_csi300_custom_step0_s_20260321_15 388611293213277441 (Recorders: 2/5)

	Recorder: fde86cd897b74db2b59a7f76c1eec1a1

		Model: {'id': 'fde86cd897b74db2b59a7f76c1eec1a1', 'model': 'LGBModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.001, 'ICIR': 0.008, 'Rank IC': 0.023, 'Rank ICIR': 0.158}, 'data_train_vec': ['2021-03-21', '2024-12-20'], 'train_time_vec': ['2026-03-21', '2026-03-21'], 'rank_icir': '0.158', 'weight': '0.039'}

	Recorder: 4a091a3d6d624e92bc1497d2d9e8fd25

		Model: {'id': '4a091a3d6d624e92bc1497d2d9e8fd25', 'model': 'LGBModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.031, 'ICIR': 0.304, 'Rank IC': 0.049, 'Rank ICIR': 0.388}, 'data_train_vec': ['2024-03-21', '2025-09-20'], 'train_time_vec': ['2026-03-21', '2026-03-21'], 'rank_icir': '0.388', 'weight': '0.096'}
Experiment: EXP_DEnsembleModel_Alpha158_csi300_custom_step0_s_20260321_13 352358604237308621 (Recorders: 3/5)

	Recorder: 3df1443e75164ed5ae49b7761d6e88f1

		Model: {'id': '3df1443e75164ed5ae49b7761d6e88f1', 'model': 'DEnsembleModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.013, 'ICIR': 0.081, 'Rank IC': 0.032, 'Rank ICIR': 0.179}, 'data_train_vec': ['2021-03-21', '2024-12-20'], 'train_time_vec': ['2026-03-21', '2026-03-21'], 'rank_icir': '0.179', 'weight': '0.044'}

	Recorder: f3a73b408780484692528bdc997e91c3

		Model: {'id': 'f3a73b408780484692528bdc997e91c3', 'model': 'DEnsembleModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.038, 'ICIR': 0.37, 'Rank IC': 0.043, 'Rank ICIR': 0.37}, 'data_train_vec': ['2024-03-21', '2025-09-20'], 'train_time_vec': ['2026-03-21', '2026-03-21'], 'rank_icir': '0.370', 'weight': '0.092'}

	Recorder: f609d342486341bb8b6292dd3e506f63

		Model: {'id': 'f609d342486341bb8b6292dd3e506f63', 'model': 'DEnsembleModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.005, 'ICIR': 0.042, 'Rank IC': 0.018, 'Rank ICIR': 0.209}, 'data_train_vec': ['2025-03-21', '2025-12-20'], 'train_time_vec': ['2026-03-21', '2026-03-21'], 'rank_icir': '0.209', 'weight': '0.052'}
Experiment: EXP_LinearModel_Alpha158_csi300_custom_step0_s_20260321_13 576492816078798887 (Recorders: 5/5)

	Recorder: fd8a2e5bde4b43039e278717cc4fe1f3

		Model: {'id': 'fd8a2e5bde4b43039e278717cc4fe1f3', 'model': 'LinearModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.017, 'ICIR': 0.132, 'Rank IC': 0.023, 'Rank ICIR': 0.201}, 'data_train_vec': ['2021-03-21', '2024-12-20'], 'train_time_vec': ['2026-03-21', '2026-03-21'], 'rank_icir': '0.201', 'weight': '0.050'}

	Recorder: 5069bcea073e4fd0a8d001f26e8f2946

		Model: {'id': '5069bcea073e4fd0a8d001f26e8f2946', 'model': 'LinearModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.007, 'ICIR': 0.061, 'Rank IC': 0.02, 'Rank ICIR': 0.179}, 'data_train_vec': ['2022-03-21', '2025-03-20'], 'train_time_vec': ['2026-03-21', '2026-03-21'], 'rank_icir': '0.179', 'weight': '0.044'}

	Recorder: 9eeb9c74076c426193eb915658f68fa2

		Model: {'id': '9eeb9c74076c426193eb915658f68fa2', 'model': 'LinearModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.012, 'ICIR': 0.097, 'Rank IC': 0.034, 'Rank ICIR': 0.307}, 'data_train_vec': ['2023-03-21', '2025-06-20'], 'train_time_vec': ['2026-03-21', '2026-03-21'], 'rank_icir': '0.307', 'weight': '0.076'}

	Recorder: 1cef1397518c44a4878d7ed9d0d748f4

		Model: {'id': '1cef1397518c44a4878d7ed9d0d748f4', 'model': 'LinearModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.014, 'ICIR': 0.112, 'Rank IC': 0.016, 'Rank ICIR': 0.148}, 'data_train_vec': ['2024-03-21', '2025-09-20'], 'train_time_vec': ['2026-03-21', '2026-03-21'], 'rank_icir': '0.148', 'weight': '0.037'}

	Recorder: f171b7dc5e59421d9ee408788e53dd9d

		Model: {'id': 'f171b7dc5e59421d9ee408788e53dd9d', 'model': 'LinearModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.023, 'ICIR': 0.224, 'Rank IC': 0.038, 'Rank ICIR': 0.377}, 'data_train_vec': ['2025-03-21', '2025-12-20'], 'train_time_vec': ['2026-03-21', '2026-03-21'], 'rank_icir': '0.377', 'weight': '0.094'}
Experiment: EXP_XGBModel_Alpha158_csi300_custom_step0_s_20260321_13 295968150635312923 (Recorders: 2/5)

	Recorder: 3609c2ae7ff94ab688aef8d16348d554

		Model: {'id': '3609c2ae7ff94ab688aef8d16348d554', 'model': 'XGBModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.017, 'ICIR': 0.158, 'Rank IC': 0.038, 'Rank ICIR': 0.327}, 'data_train_vec': ['2024-03-21', '2025-09-20'], 'train_time_vec': ['2026-03-21', '2026-03-21'], 'rank_icir': '0.327', 'weight': '0.081'}

	Recorder: afa72cd472ae4a8d8aa0b8240c684d04

		Model: {'id': 'afa72cd472ae4a8d8aa0b8240c684d04', 'model': 'XGBModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.03, 'ICIR': 0.357, 'Rank IC': 0.07, 'Rank ICIR': 0.959}, 'data_train_vec': ['2025-03-21', '2025-12-20'], 'train_time_vec': ['2026-03-21', '2026-03-21'], 'rank_icir': '0.959', 'weight': '0.238'}
