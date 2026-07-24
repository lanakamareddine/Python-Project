## Spike Threshold Detector and Time Stamp Generator

# Background: 
The project aims to implement a spike detection code for neural recordings using Python.
The threshold for each channel is calculated using the Median Absolute Deviation (MAD). 
Using the functions below, we are able to generate timestamps for spikes (in milliseconds).

# Files:
- rawdata01.mat – raw data of channel recordings
- READ Me.Final Version - Project Read Me file
- FinalVersion - Code File using BW Jupyter

# Packages:
- Numpy
- SciPy (Loadmat)
- Matplotlib

Note: Use Loadmat to convert the raw data from .mat files in order to be visualized in Python.

# Functions
auto_threshold(x, k=4) --> to calculate the detection threshold for a single channel using the MAD

spike_detect(d, si, thresholds) --> to detect spikes by identifying threshold crossings and returning the spike timestamps for every channel.


# How the Code Runs - Spike Detector
The spike detector performs the following steps:

1. Import the raw data from the MATLAB file.
2. Plot the raw recordings to visualize the signal from each channel.
3. Calculate a separate detection threshold for each recording channel using the Median Absolute Deviation (MAD).
4. Calculate both positive and negative thresholds using the estimated noise level.
5. Select the threshold (positive or negative) with the greater number of crossings for each channel.
6. Loop through every sample in each recording channel.
7. Detect the first threshold crossing by comparing each sample with the previous sample.
8. Store the spike timestamps for each channel in a dictionary.
9. Return the spike timestamps and the thresholds used for detection


# Authors 
Zhenni Jin, Subin Lee, Lana Kamareddine 
SoSe 2026 - Python: Basic Programming Module



