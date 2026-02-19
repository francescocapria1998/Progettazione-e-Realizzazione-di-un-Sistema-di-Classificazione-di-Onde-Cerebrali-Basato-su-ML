This script analyzes the impact of training data scarcity on the performance of a Residual Neural Network (ResNet) applied to the classification of EEG signals represented through Power Spectral Density (PSD) features.
The goal is to evaluate how the model’s performance evolves as the amount of available training data progressively increases, while keeping the test dataset fixed.

The classifier used is a ResNet, consistent with the previous experiments, and the experimental protocol is defined as follows:


- Input Data: 
	- PSD datasets extracted from 27 subjects;

- Train/Test Split:
	- A single stratified split (50% training, 50% testing);
	- A fixed test set shared across all experiments;

- Training Set Partitioning:
	- The training set is divided into 10 disjoint and stratified partitions (P1–P10);
	- Incremental training is performed by progressively increasing the number of training partitions used;