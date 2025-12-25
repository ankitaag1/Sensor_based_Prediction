# Sensor_based_Prediction
Code for the analysis done in the published paper 'Sensor-Based Prediction of Mental Effort during Learning from Physiological Data: A Longitudinal Case Study' https://www.mdpi.com/2624-6120/2/4/51

In the notebooks, add the name of your datafile in .csv format in the line: df = pd.read_csv(" ") before running the code.

This repository contains chronologically ordered sensor data and multiple modeling approaches for predicting student's mental effort during different activities.

📁 Data Format

Input file: Sensor-based prediction dataset (CSV)

Row order: Chronological (time-ordered) — no shuffling

Column structure:

Column 1 (Target)
In_solving_or_studying_the_topics_in_lecture_I_invested

Predictor variables:

accx – Accelerometer X-axis

accy – Accelerometer Y-axis

accz – Accelerometer Z-axis

eda_f – Electrodermal activity (filtered)

temp_f – Skin temperature (filtered)

HR – Heart rate

The dataset is suitable for time-series regression and state transition analysis.

📓 Notebooks Overview
🔹 sensor_traditional.ipynb

Implements traditional machine learning models using time-ordered train/test splits:

K-Nearest Neighbors (KNN)

Logistic Regression (LR)

Random Forest (RF)

Key features:

No random shuffling (order preserved)

Evaluation using RMSE, R², F1-score

Suitable for baseline comparisons

🔹 sensor_RNNLSTM.ipynb

Implements deep learning sequence models:

Recurrent Neural Network (RNN)

Long Short-Term Memory (LSTM)

Key features:

Sliding-window sequence generation

Chronological train/test splits (10%–90%)

Regression-based prediction

Transition detection from predicted signals

🔹 sensor_CNN.ipynb

Implements 1D Convolutional Neural Networks (CNN) for sensor-based time-series modeling.

Key features:

Temporal convolution over sensor windows

Comparable evaluation metrics (RMSE, R², F1)

Designed for efficient feature extraction from multivariate sensor data
