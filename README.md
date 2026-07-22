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

1. Load the intracellular recording.
2. Convert the sample index into a timestamp (milliseconds).
3. Calculate one threshold for each channel using the Median Absolute Deviation (MAD).
4. Estimate the noise level by dividing the MAD by 0.6745.
5. Loop through every sample in each channel.
6. Detect the first threshold crossing:
   - upward crossing for positive thresholds
   - downward crossing for negative thresholds
7. Store the spike timestamps for each channel.
8. Return the detected spike timestamps.

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
 
