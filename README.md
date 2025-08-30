# FX Time Series Forecasting with CNN-Transformer

A Master in Science course in Deep Learning group project which implements a hybrid model combining Convolutional Neural Networks (CNNs) and Transformers for forecasting foreign exchange (FX) time series data. The approach is adapted from the paper ["Financial Time Series Forecasting using CNN and Transformer"](https://arxiv.org/pdf/2304.04912), which demonstrated superior performance in predicting intraday price movements by capturing both short-term and long-term dependencies.

## Overview

- **Objective**: Predict the future direction of FX prices (up or down) based on historical data.
- **Model Architecture**:
  - **CNN**: Extracts local patterns to model short-term dependencies.
  - **Transformer**: Captures global context and long-term dependencies.
- **Dataset**: Historical USDJPY FX data sampled at daily intervals.

## Methodology

1. **Data Preprocessing**:
   - Normalize and structure FX data into sequences suitable for model input.
   - Create feature engineered variables (lags, momentum, trend, volatility, volume , etc)
   - Label each sequence with the corresponding future price movement (binary forward classification)

2. **Model Architecture**:
   - **CNN Layer**: 1D convolutional filters capture local temporal patterns.
   - **Transformer Encoder**: Processes CNN-extracted features to model long-range dependencies.
   - **Output Layer**: Classifies future price movement (up or down)

3. **Training**:
   - Split data into training and validation sets.
   - Train with binary cross-entropy loss.

4. **Evaluation**:
   - Metrics: Accuracy and AUC
   - Test Set achieved a 64.43% accuracy with 0.64 AUC
