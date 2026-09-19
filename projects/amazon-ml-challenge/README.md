# Amazon ML Challenge - Large-Scale Product Classification

Large-scale multi-class product-category classification using product metadata, multilingual text preprocessing, sentence embeddings, GPU-accelerated nearest-neighbor classification, and prediction ensembling.

## Problem

The task is to predict a product's `BROWSE_NODE_ID` from text metadata including:

- `TITLE`
- `DESCRIPTION`
- `BULLET_POINTS`
- `BRAND`

The training data contains roughly 2.9 million products across approximately 9,900 categories.

## Approach

### 1. Text preprocessing

Clean product text, normalize noisy characters, handle non-English content, and prepare fields for downstream embedding generation.

### 2. Sentence embeddings

Represent product text using 384-dimensional sentence embeddings from pretrained Sentence-Transformer models.

### 3. Classification

Train GPU-accelerated KNN-style classifiers over the embedding space and compare alternative approaches.

### 4. Ensembling

Combine multiple model predictions using majority voting to produce the final submission.

## Results

The original project records a best submission accuracy of **66.85%**. The supplied repository includes the corresponding submission and leaderboard evidence.

## Project structure

```text
notebooks/
  amazon-ml-preprocessing.ipynb
  amazon_ml_translation_csv.ipynb
  amazon_ml_embeddings.ipynb
  amazon_ml_training.ipynb
  amazon_ml_mode.ipynb
leaderboard/
submission_top-score.csv
```

## Tech stack

Python, pandas, NumPy, scikit-learn, Sentence-Transformers, GPU acceleration, multilingual text-processing tools.

## Engineering challenges

At this scale, the main challenge is not only model selection. Text normalization, embedding generation, memory usage, class cardinality, inference cost, and ensemble consistency all become important parts of the system.

## Reproduction

The notebooks are intended to be executed as a pipeline. Competition datasets are not redistributed here. Download the permitted data from the competition source, update local paths, then execute preprocessing, embedding, training, and ensemble notebooks in sequence.
