# SIIM-FISABIO-RSNA COVID-19 Detection

Computer-vision pipeline for the SIIM-FISABIO-RSNA COVID-19 Kaggle competition, combining study-level chest X-ray classification with image-level abnormality detection.

> **Research/educational project.** This repository is not a medical diagnostic system and model outputs should not be interpreted as clinical advice.

## Problem

The competition required two related tasks:

- classify chest radiographs into study-level appearance categories
- localize image-level abnormalities with bounding boxes

The project combines both predictions in a final inference pipeline.

## Pipeline

### 1. Data preparation

DICOM chest scans are converted into model-ready image representations and associated metadata is organized into tabular files.

### 2. Exploratory analysis

Class distributions, image characteristics, metadata fields, and label structure are examined before modeling.

### 3. Study-level classification

Multiple pretrained TensorFlow backbones are evaluated for the four study-level categories:

- Negative for Pneumonia
- Typical Appearance
- Indeterminate Appearance
- Atypical Appearance

### 4. Image-level detection

YOLOv5 is trained to localize abnormalities. Experiments use multiple image resolutions and cross-validation, with experiment tracking through Weights & Biases.

### 5. Final inference

Study-level classification and image-level detection outputs are combined for held-out test scans.

## Repository structure

```text
notebooks/
  siim-covid-19-data-preparation.ipynb
  siim-covid-19-data-visualization.ipynb
  siim-covid-19-study-level-predictions.ipynb
  siim-covid-19-yolo-v5-image-level-predictions.ipynb
  siim-covid-19-final-inference.ipynb
```

## Tech stack

Python, TensorFlow/Keras, YOLOv5, OpenCV, pandas, NumPy, matplotlib, seaborn, Weights & Biases, DICOM tooling.

## Key engineering points

- Separates study-level classification from image-level localization.
- Uses cross-validation for object-detection experiments.
- Preserves the distinction between per-study and per-image labels.
- Produces a combined inference pipeline instead of treating the tasks independently.

## Data and model artifacts

The original competition dataset and trained weights are intentionally not bundled into this portfolio documentation. Obtain data through the official competition source and reproduce the preparation/training pipeline locally.

## Disclaimer

This work is for machine-learning research and educational use. It has not been validated for clinical deployment.
