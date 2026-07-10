# Spike Threshold Detector & Time Stamp Generator 
## Background: 
This program detects action potentials ("spikes") in multi-channel electrophysiological recordings. For each channel, it finds every moment the signal crosses a threshold and returns a **time stamp list (`tsl`)** — the times (in milliseconds) at which spikes occurred.

It automatically:
- Handles **any number of channels** (columns) in the raw data
- Figures out whether spikes in a channel go **up** (positive-going) or
  **down** (negative-going), and sets an appropriate threshold for each
  channel automatically using a statistical method (MAD — see below)
- Removes false double-detections caused by noise wobbling across the
  threshold, using a refractory period filter
