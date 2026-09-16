# EEG Motor Imagery Classification

A Brain-Computer Interface (BCI) project that processes EEG signals and classifies imagined left-hand and right-hand movements using signal processing and machine learning.

## Overview

This project explores motor imagery classification from EEG recordings. The pipeline preprocesses multi-channel EEG signals, extracts discriminative spatial features using Common Spatial Patterns (CSP), and trains a Linear Discriminant Analysis (LDA) classifier to distinguish between left-hand and right-hand motor imagery.

The project was developed in Python using Google Colab.

## Features

- Loads EEG motor imagery data from MATLAB `.mat` files
- Processes 68-channel EEG recordings sampled at 512 Hz
- Separates recordings into left-hand and right-hand motor imagery trials
- Applies an 8–30 Hz Butterworth bandpass filter
- Extracts EEG features using log variance and Common Spatial Patterns (CSP)
- Uses sliding-window segmentation for additional training samples
- Trains an LDA classifier for binary motor imagery classification
- Evaluates model performance on held-out test data
- Visualizes EEG electrode positions and investigates motor-cortex channels

## Machine Learning Pipeline

1. Load EEG recordings
2. Separate left-hand and right-hand motor imagery trials
3. Apply an 8–30 Hz bandpass filter
4. Split the dataset into training and testing sets
5. Generate additional training epochs using a sliding window
6. Extract spatial features using CSP
7. Train an LDA classifier
8. Evaluate predictions on unseen EEG trials

## Technologies

- Python
- NumPy
- SciPy
- Scikit-learn
- MNE
- Matplotlib
- Google Colab

## Model

The classification pipeline uses:

**Common Spatial Patterns (CSP)** to identify spatial patterns in EEG activity that help distinguish between left-hand and right-hand motor imagery.

**Linear Discriminant Analysis (LDA)** to classify the CSP features into the two motor imagery classes.

## Signal Processing

EEG signals are filtered between **8–30 Hz**, covering frequency ranges commonly analyzed for motor imagery signals.

The preprocessing pipeline uses a fifth-order Butterworth bandpass filter implemented with SciPy.

## Dataset Structure

Each subject contains:

- 68 EEG channels
- 512 Hz sampling rate
- 100 left-hand motor imagery trials
- 100 right-hand motor imagery trials
- 716 time points per trial

The two classes are encoded as:

- `0` — Left-hand motor imagery
- `1` — Right-hand motor imagery

## Running the Project

The notebook is designed to run in Google Colab.

Install the required dependencies:

```bash
pip install mne scipy numpy matplotlib scikit-learn
