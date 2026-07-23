# Spike Threshold Detector & Time Stamp Generator 
## Background: 

This project implements a simple spike detection algorithm for intracellular neuronal recordings in Python.

The algorithm detects spikes by identifying the first time the signal crosses a threshold. A separate threshold is calculated for each recording channel using the Median Absolute Deviation (MAD). The detected spike locations are returned as timestamps in milliseconds.

---

## Project Files

- `rawdata01.mat` – Raw extracellular recording containing two channels.
- `10_Project_spike_threshold.ipynb` – Main notebook containing the spike detection program.
- `README.md` – Project documentation.

---

## Requirements

The project requires the following Python packages:

- NumPy
- SciPy
-    Loadmat
- Matplotlib 

Note: Use Loadmat to convert the raw data from .mat files in order to be visualized in Python.

---

## Spike Detector

The spike detector performs the following steps:

1. Import the raw data from the MATLAB file.
2. Plot the raw recordings to visualize the signal from each channel.
3. Calculate a separate detection threshold for each recording channel using the Median Absolute Deviation (MAD).
4. Estimate the background noise by dividing the MAD by 0.6745.
5. Calculate both positive and negative thresholds using the estimated noise level.
6. Select the threshold (positive or negative) with the greater number of crossings for each channel.
7. Loop through every sample in each recording channel.
8. Detect the first threshold crossing by comparing each sample with the previous sample.
9. Convert the detected sample indices into timestamps in milliseconds.
10. Store the spike timestamps for each channel in a dictionary.
11. Return the spike timestamps and the thresholds used for detection.

## Functions

### `auto_threshold(x, k=4)`

Calculates the detection threshold for a single channel using the Median Absolute Deviation (MAD).

### `spike_detect(d, si, thresholds)`

Detects spikes by identifying threshold crossings and returns the spike timestamps for each recording channel.

---

## Limitations

Some limitations include:

- Noise may produce false detections.
- Small spikes may not exceed the threshold.
- Detection depends on the chosen threshold coefficient (`k`).

---

## Authors

**Zhenni Jin, Subin Lee, Lana Kamareddine**
SoSe 2026 - Python: Basic Programming Module
 
