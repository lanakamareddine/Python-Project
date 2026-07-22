# Spike Threshold Detector & Time Stamp Generator 
## Background: 

This project implements a simple spike detection algorithm for intracellular neuronal recordings in Python.

The algorithm detects spikes by identifying the first time the signal crosses a threshold. A separate threshold is calculated for each recording channel using the Median Absolute Deviation (MAD). The detected spike locations are returned as timestamps in milliseconds.

The project was implemented using basic Python programming concepts, including loops, conditionals, lists, dictionaries, and NumPy.

---

## Project Files

- `rawdata01.mat` – Raw extracellular recording containing two channels.
- `10_Project_spike_threshold.ipynb` – Main notebook containing the spike detection algorithm.
- `README.md` – Project documentation.

---

## Requirements

The project requires the following Python packages:

- NumPy
- SciPy
- Matplotlib

Install them using:

```bash
pip install numpy scipy matplotlib
```

---

## Algorithm

The spike detector performs the following steps:

1. Load the extracellular recording.
2. Calculate one threshold for each channel using the Median Absolute Deviation (MAD).
3. Estimate the noise level by dividing the MAD by 0.6745.
4. Loop through every sample in each channel.
5. Detect the first threshold crossing:
   - upward crossing for positive thresholds
   - downward crossing for negative thresholds
6. Convert the sample index into a timestamp (milliseconds).
7. Store the spike timestamps for each channel.
8. Return the detected spike timestamps.

---

## Threshold Calculation

For each channel, the threshold is calculated as follows:

1. Compute the median of the signal.
2. Compute the Median Absolute Deviation (MAD).
3. Estimate the background noise:

```
Noise estimate = MAD / 0.6745
```

4. Calculate the threshold:

```
Threshold = Median ± k × Noise Estimate
```

where **k = 4**.

---

## Output

The function returns a dictionary containing the detected spike timestamps for each recording channel.

Example:

```python
{
    0: array([10.39, 28.61, 44.15]),
    1: array([7.82, 35.74, 61.18])
}
```

The dictionary keys represent the channel numbers, and the values are NumPy arrays containing the spike timestamps in milliseconds.

---

## Functions

### `auto_threshold(x, k=4)`

Calculates the detection threshold for a single channel using the Median Absolute Deviation (MAD).

### `spike_detect(d, si, thresholds)`

Detects spikes by identifying threshold crossings and returns the spike timestamps for each recording channel.

---

## Limitations

This detector uses a simple threshold-crossing approach.

Some limitations include:

- Noise may produce false detections.
- Small spikes may not exceed the threshold.
- Detection depends on the chosen threshold coefficient (`k`).
- The algorithm detects spikes but does not perform spike sorting or classify spikes from different neurons.

---

## Authors

**Zhenni Jin, Subin Lee, Lana Kamareddine**
 
University of Tübingen
