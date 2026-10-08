# Reproduction of the best NIR result from the manuscript
Original notebook: DINOv2_PCA_Comparison_Colab.ipynb (unmodified).
Result: NIR_spe / Com_PCA, accuracy 0.8506024096, macro-F1 0.806352.
Frozen DINOv2 → embeddings → StandardScaler → PCA → RBF-SVM.
10 external folds without shuffling, 3 internal folds. Components and classifier chosen within the training set. These are internal validation results, not external validation.

	1. Extract this package and open the notebook in Google Colab.

	2. Run the cells in the original order; the notebook installs the dependencies.

	3. When prompted for data, load labels.npy, NIR_spe_embeddings.npy, and 	Combined_spe_embeddings.npy from the inputs folder (you can select them together).

	4. Keep the original configuration to repeat NIR and Combined. For NIR only, set DATASETS=["NIR_spe"].

	5. Look up NIR_spe / Com_PCA in the generated summary. reference_results contains the original predictions, summary, and contract for comparison.

The notebook uses DINOv2 embeddings that have already been extracted and verified via SHA-256. This PCA/classification step runs on the CPU and does not re-run the encoder; DINOv2 weights or a GPU are not required. To reproduce starting from the spectra, the previous extraction notebook would be needed, which is not part of this minimal package.

No models, .env, or credentials included. Numerical embedding data and predictions are included to allow reproduction; share according to data usage permissions. Numerical identity across different versions/environments is not guaranteed.