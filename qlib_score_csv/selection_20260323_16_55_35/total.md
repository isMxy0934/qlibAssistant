# params 
 {'predict_dates': [{'start': '2026-03-23', 'end': '2026-03-23'}], 'provider_uri': '~/.qlib/qlib_data/cn_data/', 'uri_folder': '~/.qlibAssistant/mlruns/', 'analysis_folder': '~/.qlibAssistant/analysis/', 'pfx_name': 'p', 'sfx_name': 's', 'model_name': 'Linear', 'dataset_name': 'Alpha158', 'stock_pool': 'csi300', 'step': 60, 'rolling_type': 'expanding', 'model_filter': ['.*'], 'rec_filter': [{'ic': 0.001}, {'icir': 0.001}, {'rankic': 0.001}, {'rankicir': 0.001}]}



 # model info 

Experiment: EXP_CatBoostModel_Alpha158_csi300_custom_step0_s_20260323_16 777749891248702458 (Recorders: 3/5)

	Recorder: 7683e561d6974f4d932c7f29b85d7870

		Model: {'id': '7683e561d6974f4d932c7f29b85d7870', 'model': 'CatBoostModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.008, 'ICIR': 0.055, 'Rank IC': 0.023, 'Rank ICIR': 0.152}, 'data_train_vec': ['2021-03-23', '2024-12-22'], 'train_time_vec': ['2026-03-23', '2026-03-23'], 'rank_icir': '0.152', 'weight': '0.037'}

	Recorder: 46b287f2df4345a9ba62301fdf68da67

		Model: {'id': '46b287f2df4345a9ba62301fdf68da67', 'model': 'CatBoostModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.022, 'ICIR': 0.165, 'Rank IC': 0.058, 'Rank ICIR': 0.37}, 'data_train_vec': ['2024-03-23', '2025-09-22'], 'train_time_vec': ['2026-03-23', '2026-03-23'], 'rank_icir': '0.370', 'weight': '0.090'}

	Recorder: 654a0617cb784d819e44f621a70b7049

		Model: {'id': '654a0617cb784d819e44f621a70b7049', 'model': 'CatBoostModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.015, 'ICIR': 0.137, 'Rank IC': 0.038, 'Rank ICIR': 0.285}, 'data_train_vec': ['2025-03-23', '2025-12-22'], 'train_time_vec': ['2026-03-23', '2026-03-23'], 'rank_icir': '0.285', 'weight': '0.069'}
Experiment: EXP_LGBModel_Alpha158_csi300_custom_step0_s_20260323_16 533446897113201992 (Recorders: 2/5)

	Recorder: 8331e670097340b0a47183fadc36931f

		Model: {'id': '8331e670097340b0a47183fadc36931f', 'model': 'LGBModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.01, 'ICIR': 0.067, 'Rank IC': 0.031, 'Rank ICIR': 0.192}, 'data_train_vec': ['2021-03-23', '2024-12-22'], 'train_time_vec': ['2026-03-23', '2026-03-23'], 'rank_icir': '0.192', 'weight': '0.046'}

	Recorder: a3b6dc64ee5c4baf9d9e15bc05469687

		Model: {'id': 'a3b6dc64ee5c4baf9d9e15bc05469687', 'model': 'LGBModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.023, 'ICIR': 0.268, 'Rank IC': 0.044, 'Rank ICIR': 0.383}, 'data_train_vec': ['2024-03-23', '2025-09-22'], 'train_time_vec': ['2026-03-23', '2026-03-23'], 'rank_icir': '0.383', 'weight': '0.093'}
Experiment: EXP_DEnsembleModel_Alpha158_csi300_custom_step0_s_20260323_13 585396576822391313 (Recorders: 2/5)

	Recorder: 62133f41a3c945f1b5f1d6fad65ff188

		Model: {'id': '62133f41a3c945f1b5f1d6fad65ff188', 'model': 'DEnsembleModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.017, 'ICIR': 0.105, 'Rank IC': 0.034, 'Rank ICIR': 0.19}, 'data_train_vec': ['2021-03-23', '2024-12-22'], 'train_time_vec': ['2026-03-23', '2026-03-23'], 'rank_icir': '0.190', 'weight': '0.046'}

	Recorder: c405a274359f497fbe0ecaad05e2aa18

		Model: {'id': 'c405a274359f497fbe0ecaad05e2aa18', 'model': 'DEnsembleModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.029, 'ICIR': 0.278, 'Rank IC': 0.04, 'Rank ICIR': 0.349}, 'data_train_vec': ['2024-03-23', '2025-09-22'], 'train_time_vec': ['2026-03-23', '2026-03-23'], 'rank_icir': '0.349', 'weight': '0.084'}
Experiment: EXP_LinearModel_Alpha158_csi300_custom_step0_s_20260323_13 558994040632380153 (Recorders: 5/5)

	Recorder: 7d43fb2be41742d0982aedb2ecc1240e

		Model: {'id': '7d43fb2be41742d0982aedb2ecc1240e', 'model': 'LinearModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.02, 'ICIR': 0.16, 'Rank IC': 0.026, 'Rank ICIR': 0.231}, 'data_train_vec': ['2021-03-23', '2024-12-22'], 'train_time_vec': ['2026-03-23', '2026-03-23'], 'rank_icir': '0.231', 'weight': '0.056'}

	Recorder: 5fa9c34a03b84c94ad09837e52bbe701

		Model: {'id': '5fa9c34a03b84c94ad09837e52bbe701', 'model': 'LinearModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.008, 'ICIR': 0.061, 'Rank IC': 0.02, 'Rank ICIR': 0.174}, 'data_train_vec': ['2022-03-23', '2025-03-22'], 'train_time_vec': ['2026-03-23', '2026-03-23'], 'rank_icir': '0.174', 'weight': '0.042'}

	Recorder: 2933a10e9515431fa1284c180d950ee8

		Model: {'id': '2933a10e9515431fa1284c180d950ee8', 'model': 'LinearModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.016, 'ICIR': 0.122, 'Rank IC': 0.038, 'Rank ICIR': 0.344}, 'data_train_vec': ['2023-03-23', '2025-06-22'], 'train_time_vec': ['2026-03-23', '2026-03-23'], 'rank_icir': '0.344', 'weight': '0.083'}

	Recorder: 022497607f9a4c2cb3e7836f4d3124d8

		Model: {'id': '022497607f9a4c2cb3e7836f4d3124d8', 'model': 'LinearModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.017, 'ICIR': 0.126, 'Rank IC': 0.021, 'Rank ICIR': 0.18}, 'data_train_vec': ['2024-03-23', '2025-09-22'], 'train_time_vec': ['2026-03-23', '2026-03-23'], 'rank_icir': '0.180', 'weight': '0.044'}

	Recorder: cd7e26036831498ea6a6c5bb7810b531

		Model: {'id': 'cd7e26036831498ea6a6c5bb7810b531', 'model': 'LinearModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.017, 'ICIR': 0.162, 'Rank IC': 0.026, 'Rank ICIR': 0.269}, 'data_train_vec': ['2025-03-23', '2025-12-22'], 'train_time_vec': ['2026-03-23', '2026-03-23'], 'rank_icir': '0.269', 'weight': '0.065'}
Experiment: EXP_XGBModel_Alpha158_csi300_custom_step0_s_20260323_13 479430937983570311 (Recorders: 3/5)

	Recorder: e0465cef394f48949fffb7cfac130fb8

		Model: {'id': 'e0465cef394f48949fffb7cfac130fb8', 'model': 'XGBModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.009, 'ICIR': 0.067, 'Rank IC': 0.033, 'Rank ICIR': 0.196}, 'data_train_vec': ['2021-03-23', '2024-12-22'], 'train_time_vec': ['2026-03-23', '2026-03-23'], 'rank_icir': '0.196', 'weight': '0.047'}

	Recorder: 18b3acd39ff8487ab40be1f76b06f2e0

		Model: {'id': '18b3acd39ff8487ab40be1f76b06f2e0', 'model': 'XGBModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.026, 'ICIR': 0.251, 'Rank IC': 0.048, 'Rank ICIR': 0.454}, 'data_train_vec': ['2024-03-23', '2025-09-22'], 'train_time_vec': ['2026-03-23', '2026-03-23'], 'rank_icir': '0.454', 'weight': '0.110'}

	Recorder: b529fd9b29784755bb1507208f0a132d

		Model: {'id': 'b529fd9b29784755bb1507208f0a132d', 'model': 'XGBModel', 'dataset': 'Alpha158', 'ic_info': {'IC': 0.019, 'ICIR': 0.251, 'Rank IC': 0.022, 'Rank ICIR': 0.365}, 'data_train_vec': ['2025-03-23', '2025-12-22'], 'train_time_vec': ['2026-03-23', '2026-03-23'], 'rank_icir': '0.365', 'weight': '0.088'}
