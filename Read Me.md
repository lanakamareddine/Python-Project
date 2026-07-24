## Spike Threshold Detector and Time Stamp Generator

# Background: 
The project aims to implement a spike detection code for neural recordings using Python.
The threshold for each channel is calculated using the Median Absolute Deviation (MAD). 
Using the functions below, we are able to generate timestamps for spikes (in milliseconds).

# Files:
- rawdata01.mat – raw data of channel recordings
- READ Me.Final Version - Project Read Me file
- kk

# Packages:
- Numpy
- SciPy (Loadmat)
- Matplotlib

Note: Use Loadmat to convert the raw data from .mat files in order to be visualized in Python.

# Functions
auto_threshold(x, k=4) --> to calculate the detection threshold for a single channel using the MAD

spike_detect(d, si, thresholds) --> to detect spikes by identifying threshold crossings and returning the spike timestamps for every channel.

# Authors 
Zhenni Jin, Subin Lee, Lana Kamareddine 
SoSe 2026 - Python: Basic Programming Module



