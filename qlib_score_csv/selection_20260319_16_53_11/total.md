# params 
 {'predict_dates': [{'start': '2026-03-19', 'end': '2026-03-19'}], 'provider_uri': '~/.qlib/qlib_data/cn_data/', 'uri_folder': '~/.qlibAssistant/mlruns/', 'analysis_folder': '~/.qlibAssistant/analysis/', 'pfx_name': 'p', 'sfx_name': 's', 'model_name': 'Linear', 'dataset_name': 'Alpha158', 'stock_pool': 'csi300', 'step': 60, 'rolling_type': 'expanding', 'model_filter': ['.*'], 'rec_filter': [{'ic': 0.001}, {'icir': 0.001}, {'rankic': 0.001}, {'rankicir': 0.001}]}



 # model info 

Experiment: EXP_CatBoostModel_Alpha158_csi300_custom_step0_s_20260319_16 745556128237290394 (Recorders: 3/5)

	Recorder: 5bf5cc27ac8b46d6adbb202577082ba3

		Model: {'id': '5bf5cc27ac8b46d6adbb202577082ba3', 'model': 'CatBoostModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.006, 'ICIR': 0.038, 'Rank IC': 0.029, 'Rank ICIR': 0.145}, 'data_train_vec': ['2021-03-19', '2024-12-18'], 'train_time_vec': ['2026-03-19', '2026-03-19'], 'rank_icir': '0.145', 'weight': '0.036'}

	Recorder: 1d3a627812424b428f5747448f316c09

		Model: {'id': '1d3a627812424b428f5747448f316c09', 'model': 'CatBoostModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.036, 'ICIR': 0.314, 'Rank IC': 0.051, 'Rank ICIR': 0.417}, 'data_train_vec': ['2024-03-19', '2025-09-18'], 'train_time_vec': ['2026-03-19', '2026-03-19'], 'rank_icir': '0.417', 'weight': '0.103'}

	Recorder: 39491097341b458490ae74d389709e9c

		Model: {'id': '39491097341b458490ae74d389709e9c', 'model': 'CatBoostModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.012, 'ICIR': 0.101, 'Rank IC': 0.05, 'Rank ICIR': 0.32}, 'data_train_vec': ['2025-03-19', '2025-12-18'], 'train_time_vec': ['2026-03-19', '2026-03-19'], 'rank_icir': '0.320', 'weight': '0.079'}
Experiment: EXP_LGBModel_Alpha158_csi300_custom_step0_s_20260319_16 990424037327140018 (Recorders: 2/5)

	Recorder: c2176bab68144d27b9ff419aeba0119f

		Model: {'id': 'c2176bab68144d27b9ff419aeba0119f', 'model': 'LGBModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.026, 'ICIR': 0.228, 'Rank IC': 0.042, 'Rank ICIR': 0.308}, 'data_train_vec': ['2024-03-19', '2025-09-18'], 'train_time_vec': ['2026-03-19', '2026-03-19'], 'rank_icir': '0.308', 'weight': '0.076'}

	Recorder: 8164e3f96e6548158b96ddddf6e5f246

		Model: {'id': '8164e3f96e6548158b96ddddf6e5f246', 'model': 'LGBModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.006, 'ICIR': 0.041, 'Rank IC': 0.024, 'Rank ICIR': 0.192}, 'data_train_vec': ['2025-03-19', '2025-12-18'], 'train_time_vec': ['2026-03-19', '2026-03-19'], 'rank_icir': '0.192', 'weight': '0.048'}
Experiment: EXP_DEnsembleModel_Alpha158_csi300_custom_step0_s_20260319_13 645319722960928564 (Recorders: 4/5)

	Recorder: aef44f80ed8b4596a044bdc8f79ca16c

		Model: {'id': 'aef44f80ed8b4596a044bdc8f79ca16c', 'model': 'DEnsembleModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.016, 'ICIR': 0.101, 'Rank IC': 0.032, 'Rank ICIR': 0.187}, 'data_train_vec': ['2021-03-19', '2024-12-18'], 'train_time_vec': ['2026-03-19', '2026-03-19'], 'rank_icir': '0.187', 'weight': '0.046'}

	Recorder: 735171cab7c545c19cfd2c1b2d1c3676

		Model: {'id': '735171cab7c545c19cfd2c1b2d1c3676', 'model': 'DEnsembleModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.001, 'ICIR': 0.006, 'Rank IC': 0.023, 'Rank ICIR': 0.125}, 'data_train_vec': ['2022-03-19', '2025-03-18'], 'train_time_vec': ['2026-03-19', '2026-03-19'], 'rank_icir': '0.125', 'weight': '0.031'}

	Recorder: 8699cea1307c4c658a36015ef8db41fa

		Model: {'id': '8699cea1307c4c658a36015ef8db41fa', 'model': 'DEnsembleModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.028, 'ICIR': 0.264, 'Rank IC': 0.036, 'Rank ICIR': 0.318}, 'data_train_vec': ['2024-03-19', '2025-09-18'], 'train_time_vec': ['2026-03-19', '2026-03-19'], 'rank_icir': '0.318', 'weight': '0.079'}

	Recorder: 386f87f268f94917a164c96d8189ce79

		Model: {'id': '386f87f268f94917a164c96d8189ce79', 'model': 'DEnsembleModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.018, 'ICIR': 0.148, 'Rank IC': 0.034, 'Rank ICIR': 0.387}, 'data_train_vec': ['2025-03-19', '2025-12-18'], 'train_time_vec': ['2026-03-19', '2026-03-19'], 'rank_icir': '0.387', 'weight': '0.096'}
Experiment: EXP_LinearModel_Alpha158_csi300_custom_step0_s_20260319_13 641716984892420244 (Recorders: 5/5)

	Recorder: 78acb3b365264333bf9c4a4e570a7905

		Model: {'id': '78acb3b365264333bf9c4a4e570a7905', 'model': 'LinearModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.015, 'ICIR': 0.115, 'Rank IC': 0.02, 'Rank ICIR': 0.176}, 'data_train_vec': ['2021-03-19', '2024-12-18'], 'train_time_vec': ['2026-03-19', '2026-03-19'], 'rank_icir': '0.176', 'weight': '0.044'}

	Recorder: e706b97c2ffc4c55bef2ee7ee90a3621

		Model: {'id': 'e706b97c2ffc4c55bef2ee7ee90a3621', 'model': 'LinearModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.013, 'ICIR': 0.099, 'Rank IC': 0.022, 'Rank ICIR': 0.185}, 'data_train_vec': ['2022-03-19', '2025-03-18'], 'train_time_vec': ['2026-03-19', '2026-03-19'], 'rank_icir': '0.185', 'weight': '0.046'}

	Recorder: 30ceda8e283846e5a8ce041a444a7781

		Model: {'id': '30ceda8e283846e5a8ce041a444a7781', 'model': 'LinearModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.015, 'ICIR': 0.118, 'Rank IC': 0.037, 'Rank ICIR': 0.315}, 'data_train_vec': ['2023-03-19', '2025-06-18'], 'train_time_vec': ['2026-03-19', '2026-03-19'], 'rank_icir': '0.315', 'weight': '0.078'}

	Recorder: e5faccda8f734a8492a2427991ec6f3a

		Model: {'id': 'e5faccda8f734a8492a2427991ec6f3a', 'model': 'LinearModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.019, 'ICIR': 0.146, 'Rank IC': 0.015, 'Rank ICIR': 0.138}, 'data_train_vec': ['2024-03-19', '2025-09-18'], 'train_time_vec': ['2026-03-19', '2026-03-19'], 'rank_icir': '0.138', 'weight': '0.034'}

	Recorder: 486c766151e340838c4bf0abfee64fbf

		Model: {'id': '486c766151e340838c4bf0abfee64fbf', 'model': 'LinearModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.032, 'ICIR': 0.31, 'Rank IC': 0.044, 'Rank ICIR': 0.435}, 'data_train_vec': ['2025-03-19', '2025-12-18'], 'train_time_vec': ['2026-03-19', '2026-03-19'], 'rank_icir': '0.435', 'weight': '0.108'}
Experiment: EXP_XGBModel_Alpha158_csi300_custom_step0_s_20260319_13 496916841941495767 (Recorders: 1/5)

	Recorder: fa001f0f18ea425787d3519f53900386

		Model: {'id': 'fa001f0f18ea425787d3519f53900386', 'model': 'XGBModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.026, 'ICIR': 0.223, 'Rank IC': 0.043, 'Rank ICIR': 0.389}, 'data_train_vec': ['2024-03-19', '2025-09-18'], 'train_time_vec': ['2026-03-19', '2026-03-19'], 'rank_icir': '0.389', 'weight': '0.096'}
