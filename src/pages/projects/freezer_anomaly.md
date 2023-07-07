---
layout: ../../layouts/ProjectLayout.astro
title: "Freezer Anomaly Detection"
description: "Detect abnomal frrexer compressor cycles."
---


Keywords: Timeseries, Clustering</h4>
## Summary
In refrigeration systems, compressor cycles create a recurring pattern in
temperature recordings, causing the temperature to oscillate between high and low ranges. Any deviation from this temperature cycle may indicate potential issues with the system. This article
                    presents an anomaly detection algorithm designed to monitor changes in the temperature cycles and
                    generate alerts when abnormalities occur.

## Wavelet Decomposition 
Wavelet decomposition is used to transform the temperature waveform into the frequency domain. This technique incorporates historical information into each sample. A typical period is selected for training the Principal Component Analysis (PCA) model.

## PCA Compression and Reconstruction
PCA compresses and reconstructs the frequency waveform obtained from the wavelet decomposition.
Since the PCA model is trained on a normal operation period, it can efficiently compress and reconstruct the waveform with minimal loss. The more abnormal an observation is, the greater the loss incurred during the compression and reconstruction process.
## Mean Squared Error
The Mean Squared Error (MSE) quantifies the loss resulting from the PCA compression and reconstruction. Higher MSE values indicate a greater deviation from normal operation.
## Threshold Setting with Logistic Regression
To determine the alarm threshold, a logistic regression model is trained using previous examples of abnormal refrigeration cycles. This threshold helps to differentiate between normal and abnormal operation and trigger alerts when necessary