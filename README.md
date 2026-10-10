# SHL Hiring Assessment 2026 — Spoken English Grammar Scoring

## Overview

This project presents a machine learning pipeline developed for the **SHL Hiring Assessment 2026** to predict the grammar proficiency score of spoken-English recordings.

The task is formulated as a **continuous regression problem**, where each audio recording is assigned a grammar score between **0 and 5**.

The dataset consists of **769 labelled training recordings** and **216 evaluation recordings**. The audio files are provided as 16 kHz mono WAV recordings.

## Objective

The objective is to estimate the grammar proficiency of a speaker directly from spoken English audio by learning relationships between speech characteristics and human-provided grammar scores.

The evaluation considers both:

- **Pearson Correlation** — measures the relationship between predicted and actual scores.
- **RMSE (Root Mean Squared Error)** — measures the prediction error.

## Methodology

The proposed pipeline combines multiple complementary sources of information from the speech recordings.

### 1. Pretrained Speech Representations

Pretrained self-supervised speech models are used to extract high-level representations from the audio recordings.

These representations capture characteristics of speech that are difficult to represent using manually designed acoustic features alone.

### 2. Segment-Level Audio Representation

Instead of relying exclusively on a single representation of the complete recording, different temporal sections of the speech are considered.

This allows the model to capture variations in pronunciation, fluency, speaking patterns, and other characteristics that may occur throughout a recording.

### 3. Acoustic and Prosodic Features

Handcrafted speech features are incorporated to capture interpretable characteristics such as:

- spectral characteristics
- MFCC statistics
- energy
- pitch
- speaking activity
- silence and pause characteristics
- temporal speech properties

### 4. Regression Models

Regularized regression models are used to map the extracted representations to the continuous grammar score.

Out-of-fold predictions are generated during validation to reduce information leakage and provide a reliable basis for model combination.

### 5. Ensemble Learning

Predictions from complementary model branches are combined using a second-level ensemble.

The ensemble allows information from different speech representations and acoustic features to contribute to the final prediction.

## Validation

The modelling pipeline was evaluated using:

- Out-of-fold validation
- RMSE
- Pearson correlation
- Prediction distribution analysis
- Robustness checks
- Training-data RMSE

The validation process was designed to ensure that the ensemble was not selected solely on the performance of a single train/validation split.

## Results

The final submitted solution achieved a **public Kaggle leaderboard score of 0.3819**.

| Metric | Result |
|---|---:|
| Public Kaggle Score | **0.3819** |
| Training Dataset | 769 recordings |
| Evaluation Dataset | 216 recordings |
| Prediction Range | 0–5 |

## Project Structure

```text
shl-hiring-assessment-2026/
│
├── solution.ipynb
├── README.md
├── requirements.txt
|---Submission.csv
├── SUBMISSION_STATUS.md
└── .gitignore
