This script evaluates the performance of a Residual Neural Network (ResNet) for EEG signal classification as the number of subjects used to build the training dataset increases.

The script performs multiple training and testing sessions using datasets composed of:

- 27 subjects;
- 20 subjects;
- 15 subjects;
- 10 subjects.

For each configuration, the datasets of the selected subjects are merged, and a ResNet model is trained and evaluated independently.
All results, trained weights, and aggregated datasets are automatically saved to ensure reproducibility and traceability of the experiments.