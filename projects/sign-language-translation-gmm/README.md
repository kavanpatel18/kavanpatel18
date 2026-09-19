# Sign Language Translation using Gaussian Mixture Models

Real-time American Sign Language (ASL) alphabet recognition from webcam hand landmarks using MediaPipe-style landmark extraction and Gaussian Mixture Models (GMMs).

## Overview

The pipeline captures hand landmark coordinates from a webcam, converts them into engineered feature vectors, trains a class-conditional GMM recognizer, and performs live inference by translating recognized hand signs into letters.

## Pipeline

1. **Landmark collection**: capture labeled ASL hand poses from a webcam.
2. **Feature engineering**: normalize and transform landmark coordinates into model-ready features.
3. **GMM training**: fit a Gaussian Mixture Model for sign classification.
4. **Live inference**: run the trained model against incoming webcam frames and display the predicted letter.

## Repository contents

- `data_collector_sign_language_translator_1.ipynb` - webcam data collection
- `model_sign_language_translator_2.ipynb` - feature processing and GMM training
- `deployment_sign_language_translator_3.ipynb` - real-time inference
- `fun_hand_face_detector.ipynb` - hand/face landmark experiments
- `ASL_alphabets.xlsx` - alphabet reference data
- `gmm_model.pkl` - trained classifier
- Demo GIFs - data collection and inference demonstrations

## Tech stack

Python, OpenCV, MediaPipe, NumPy, pandas, scikit-learn, Gaussian Mixture Models.

## Running

Install the dependencies and run the notebooks in order:

```bash
pip install opencv-python mediapipe numpy pandas scikit-learn
```

For live inference, load the trained model and execute the deployment notebook. Webcam and local file paths may need to be adjusted for your environment.

## Key engineering points

- Landmark-based representation avoids training directly on raw video frames.
- GMMs provide a probabilistic representation of class-specific feature distributions.
- The pipeline separates data collection, training, and deployment, making experimentation easier.

## Limitations

This project recognizes a predefined ASL alphabet vocabulary rather than continuous sign-language sentences. Performance can vary with camera angle, lighting, hand orientation, and landmark quality.
