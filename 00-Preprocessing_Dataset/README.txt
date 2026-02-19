This script takes raw EEG data as input, acquired using the Bitbrain Diadem device, and processes them in order to obtain a structured dataset suitable for use with Machine Learning and Deep Learning algorithms.

For each subject, the processing pipeline is as follows:

- Loading the dataset and removing unnecessary information;
- Signal filtering using band-pass and notch filters;
- Temporal segmentation of the signal using a sliding-window approach;
- Extraction of frequency-domain features through Power Spectral Density (PSD)
  computation using the Welch method.
