This script performs a comparison between different classification algorithms applied to EEG data that have been previously transformed into Power Spectral Density (PSD) features.

The script can be divided into two main sections:

====== PREPROCESSING PIPELINE ======
For each subject, the following steps are applied:

1) Train/Test Split:
	- 80% training, 20% test;
	- stratified split to preserve the class distribution.

2) Feature Normalization:
	- Min-Max Scaling;
	- the scaler is fitted exclusively on the training set to avoid data leakage.

3) Class Balancing:
	- oversampling of minority classes in the training set;
	- all classes are brought to the same cardinality as the most frequent class.


====== CLASSIFIER COMPARISON =====
The following classifiers are trained and tested independently for each subject.
The classification metrics are then averaged across all subjects.

1) Random Forest:
	- classical ensemble-based Machine Learning model.

2) Support Vector Machine:
	- non-linear SVM with RBF (Radial Basis Function) kernel.

3) Multi-Layer Perceptron:
	- fully connected neural network;
	- architecture:
		- 256 → 128 → 64 neurons;
		- ReLU activation function;
		- Softmax output layer;
	- best weights are saved based on the validation loss.

4) Residual Neural Network:
	- feedforward network with skip connections;
	- architecture:
		- base Dense layer;
		- residual Dense block;
		- concatenation with the original input;
	- designed to improve training stability;
	- best weights are saved during training.