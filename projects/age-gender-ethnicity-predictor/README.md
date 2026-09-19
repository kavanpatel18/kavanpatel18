# Age, Gender & Ethnicity Predictor

A Flask web application that performs multi-output face-image classification using a MobileNetV2-based deep-learning model.

> **Responsible-use note:** predictions of demographic attributes from facial images are inherently uncertain and can encode dataset bias. This project is presented as an ML engineering experiment, not as a reliable means of determining a person's identity or attributes.

## Overview

The application accepts a face image and sends it through a MobileNetV2-based multi-output model. One forward pass produces predictions for three tasks:

- age bucket
- gender class
- ethnicity class

## Architecture

```text
Uploaded image
      |
      v
Image preprocessing (200 x 200 x 3)
      |
      v
MobileNetV2 backbone
      |
      +----> Age classification
      +----> Gender classification
      +----> Ethnicity classification
      |
      v
Flask response / web UI
```

## Tech stack

- Python
- TensorFlow / Keras
- MobileNetV2
- Flask
- HTML/CSS/JavaScript
- UTKFace dataset

## Project structure

```text
app.py
age-sex-ethnicity-detection-using-multi-ouput.ipynb
requirements.txt
Procfile
runtime.txt
templates/
static/
images/
```

## Run locally

```bash
pip install -r requirements.txt
python app.py
```

Then open the local Flask address shown by the application.

The pretrained model is distributed separately from this portfolio documentation because model artifacts can be large. If using the original project package, extract the model archive before starting the application.

## Technical notes

MobileNetV2 was selected as a comparatively lightweight backbone suitable for web deployment. The multi-output design allows several predictions to be produced from a shared visual representation.

## Limitations

The model predicts categories learned from the training distribution. Accuracy can vary substantially with image quality, pose, lighting, demographic representation, and other dataset factors. Outputs should not be treated as objective measurements of a person.
