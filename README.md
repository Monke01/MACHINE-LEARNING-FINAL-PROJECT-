# MACHINE-LEARNING-FINAL-PROJECT-

Machine Learning Course Project

Project Overview

This repository contains the Machine Learning course project, covering supervised learning, unsupervised learning, sequence modelling, and regression.

The project is divided into two reviews:

- Review 1: Patient Disease Classification using multiple machine learning classification algorithms.
- Review 2: Implementation of clustering, Hidden Markov Models (HMM), and regression using the PhysioNet 2012 ICU dataset.

Each review uses its own dataset and methodology. The results are presented separately.

---

Review 1 – Patient Disease Classification

1. Introduction

The first review focuses on predicting disease categories using patient health information. Different machine learning classification algorithms are trained and evaluated to compare their performance.

The project uses patient measurements and health alert information to classify records into five disease categories.

2. Dataset Description

Dataset: "patients_data_with_alerts.xlsx"

- Total records: 50,000
- Total columns: 13
- Target column: "Predicted Disease"
- Patient ID column: "Patient Number"

Disease Categories

1. Arrhythmia
2. Asthma
3. Diabetes Mellitus
4. Hypertension
5. Normal

The dataset contains patient measurements and alert-related information, including:

- Heart Rate (bpm)
- SpO2 Level (%)
- Systolic Blood Pressure (mmHg)
- Diastolic Blood Pressure (mmHg)
- Body Temperature (°C)
- Fall Detection
- Data Accuracy (%)
- Heart Rate Alert
- SpO2 Level Alert
- Blood Pressure Alert
- Temperature Alert

3. Data Visualization

Exploratory Data Analysis (EDA) was performed to understand the dataset and identify patterns.

The following visualizations were created:

- Donut Chart: Shows the distribution of predicted disease categories.
- Box Plot: Compares SpO2 levels across disease categories.
- Scatter Plot: Shows the relationship between systolic and diastolic blood pressure, with heart rate represented by point size.
- Histogram: Displays body temperature distribution according to temperature alerts.
- Grouped Bar Chart: Compares fall detection counts across disease categories.

These visualizations help understand the distribution of patient measurements and the relationship between different features.

4. Data Preprocessing

The following preprocessing steps were applied:

- Removed the "Patient Number" column because it is an identifier.
- Separated input features and the target variable.
- Identified numerical and categorical columns.
- Handled missing numerical values using median imputation.
- Handled missing categorical values using most-frequent imputation.
- Applied StandardScaler to numerical features.
- Applied One-Hot Encoding to categorical features.
- Used a preprocessing pipeline to combine these operations.

Train-Test Split

The dataset was divided using an 80:20 split.

Dataset| Records
Training data| 40,000
Testing data| 10,000
Total| 50,000

The split used "random_state=42" and stratification to maintain the class distribution.

5. Machine Learning Algorithms

Five classification algorithms were implemented.

Logistic Regression

A classification algorithm that estimates the probability of a record belonging to a particular class.

Decision Tree

A tree-based algorithm that makes predictions by following decision rules based on feature values.

Random Forest

An ensemble algorithm that combines multiple decision trees to improve prediction performance.

K-Nearest Neighbors (KNN)

Classifies a record based on the most common class among its nearest neighbours. The implementation uses five neighbours.

Support Vector Machine (SVM)

A classification algorithm that identifies decision boundaries between different classes. The implementation uses an RBF kernel.

6. Model Performance Evaluation

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix
- Classification Report

Performance Comparison

Algorithm| Accuracy| Precision| Recall| F1 Score
Logistic Regression| 84.69%| 84.76%| 84.69%| 84.72%
Decision Tree| 70.42%| 70.39%| 70.42%| 70.40%
Random Forest| 78.94%| 79.12%| 78.94%| 79.01%
KNN| 73.76%| 74.02%| 73.76%| 73.86%
SVM| 84.44%| 84.57%| 84.44%| 84.49%

7. Model Comparison and Results

A grouped bar chart was created to compare the accuracy, precision, recall, and F1 score of all five algorithms.

Confusion matrices were generated to compare actual and predicted classes. Classification reports were also produced to examine individual class performance.

Logistic Regression achieved the best overall performance, with an accuracy of 84.69% and an F1 score of 84.72%.

8. Sample Prediction

A sample patient record was selected from the test dataset and passed through all five trained models.

The models returned the following predictions for the selected sample:

Algorithm| Prediction
Logistic Regression| Normal
Decision Tree| Normal
Random Forest| Normal
KNN| Normal
SVM| Normal

This demonstrates how the trained models can be used to make predictions on individual patient records.

9. Review 1 Conclusion

The first review successfully implemented and compared five machine learning classification algorithms for patient disease classification.

Among the implemented models, Logistic Regression achieved the highest overall accuracy and F1 score. The project also demonstrated the importance of data preprocessing, visualization, model evaluation, and prediction.

---

Review 2 – Advanced Machine Learning Techniques

Review 2 uses the PhysioNet 2012 ICU dataset and covers three machine learning units:

- Unit 3 – Clustering
- Unit 4 – Hidden Markov Model
- Unit 5 – Regression

The dataset was prepared into separate Excel sheets for the different tasks:

- "Clustering_Features"
- "Sequence_Ready"
- "Forecast_Ready"

These tasks focus on discovering groups, modelling sequences, and predicting numerical values.

---

Unit 3 – Clustering

1. Introduction

Clustering is an unsupervised machine learning technique used to group similar data points together without predefined labels.

In this project, clustering algorithms were applied to patient data to identify groups with similar characteristics.

2. Algorithms Implemented

K-Means Clustering

K-Means divides the dataset into a predefined number of clusters.

The algorithm:

1. Selects cluster centroids.
2. Assigns each data point to its nearest centroid.
3. Recalculates the centroids.
4. Repeats the process until the clusters stabilize.

Parameters:

- "n_clusters = 3"
- "random_state = 42"
- "n_init = 10"

Agglomerative Clustering

Agglomerative Clustering is a hierarchical clustering algorithm.

It starts by treating every data point as an individual cluster and repeatedly merges the closest clusters until the required number of clusters is obtained.

Parameters:

- "n_clusters = 3"
- "linkage = "ward""

3. Data Preprocessing

The clustering dataset was prepared using:

- Missing value handling through median imputation.
- Feature scaling using StandardScaler.
- Selection of numerical features for clustering.

PCA was also applied with two components to visualize the clusters in a two-dimensional space.

4. Evaluation Metrics

The clustering algorithms were evaluated using three metrics:

- Silhouette Score: Measures how well-separated the clusters are. Higher values are better.
- Davies-Bouldin Index: Measures similarity between clusters. Lower values are better.
- Calinski-Harabasz Score: Measures the ratio of between-cluster dispersion to within-cluster dispersion. Higher values are better.

5. Results

Metric| K-Means| Agglomerative
Silhouette Score| 0.155333| 0.150771
Davies-Bouldin Index| 1.877191| 1.588663
Calinski-Harabasz Score| 432.020334| 311.478273

Cluster Sizes

Algorithm| Cluster Distribution
K-Means| 650, 655, 1195
Agglomerative| 858, 1640, 2

K-Means achieved better Silhouette and Calinski-Harabasz scores, while Agglomerative achieved a lower Davies-Bouldin Index.

K-Means also produced a more balanced cluster distribution in this experiment.

6. Unit 3 Conclusion

Both clustering algorithms were successfully implemented and evaluated. K-Means performed better on two of the three evaluation metrics and avoided the extremely small cluster produced by Agglomerative Clustering.

---

Unit 4 – Hidden Markov Model (HMM)

1. Introduction

A Hidden Markov Model is a probabilistic machine learning model used to analyse sequential data.

It is useful when the observed data is available, but the underlying states responsible for generating the observations are hidden.

In this project, HMM was used to analyse sequences of patient measurements over time.

2. Main Concepts

Hidden States

Hidden states represent underlying patterns that cannot be directly observed.

Observations

Observations are the actual measurements recorded from patients.

Initial State Probabilities

These represent the probability of starting in each hidden state.

Transition Probabilities

These represent the probability of moving from one hidden state to another.

Emission Probabilities

These describe the probability of observing particular measurements from a hidden state.

Markov Property

The Markov property assumes that the next state depends on the current state rather than the entire previous sequence of states.

3. Data Preparation

The sequence data was prepared by:

- Organizing observations by patient.
- Sorting measurements by time.
- Handling missing values.
- Scaling numerical features.
- Maintaining patient sequence boundaries.

Patient identifiers and timestamps are used to organize the observations rather than as ordinary measurement features.

4. HMM Implementation

A Gaussian Hidden Markov Model was used for modelling continuous patient measurements.

The model learns hidden-state patterns and transition probabilities from the sequential observations.

The main stages include:

1. Preparing patient sequences.
2. Initializing the HMM.
3. Training the model.
4. Estimating hidden states.
5. Analysing state transitions and sequence probabilities.

5. HMM Algorithms

The main algorithms associated with HMM include:

- Forward Algorithm: Calculates the probability of an observation sequence.
- Forward-Backward Algorithm: Calculates posterior probabilities of hidden states using observations.
- Viterbi Algorithm: Finds the most likely sequence of hidden states.
- Baum-Welch Algorithm: Estimates HMM parameters during training using the Expectation-Maximization approach.

6. Unit 4 Conclusion

The Hidden Markov Model demonstrates how sequential patient measurements can be used to identify underlying statistical patterns and transitions over time.

The hidden states represent model-inferred patterns and should not be interpreted as medical diagnoses.

---

Unit 5 – Regression

1. Introduction

Regression is a supervised machine learning technique used to predict continuous numerical values.

In this project, regression models were implemented to predict the next heart rate value using patient measurement data.

Target variable: "Next Heart Rate (bpm)"

2. Algorithms Implemented

Random Forest Regressor

Uses multiple decision trees and averages their predictions to produce a final numerical result.

Parameters:

- "n_estimators = 150"
- "random_state = 42"
- "n_jobs = -1"

Extra Trees Regressor

Uses multiple randomized decision trees and combines their predictions.

Parameters:

- "n_estimators = 150"
- "random_state = 42"
- "n_jobs = -1"

Gradient Boosting Regressor

Builds decision trees sequentially, where each new tree attempts to correct errors made by the previous trees.

Parameters:

- "n_estimators = 100"
- "learning_rate = 0.05"
- "random_state = 42"

Voting Regressor

Combines predictions from multiple regression models.

In this project, it combines:

- Random Forest Regressor
- Extra Trees Regressor
- Gradient Boosting Regressor

The final prediction is obtained by averaging the predictions of the individual models.

3. Data Preprocessing

The regression dataset was prepared using:

- Missing value handling.
- Numerical feature preparation.
- Patient-wise training and testing separation.
- Removal of identifiers and target-related information from the input features where appropriate.

Patient-wise splitting helps prevent observations from the same patient appearing in both training and testing data.

4. Evaluation Metrics

The models were evaluated using:

Mean Absolute Error (MAE)

Measures the average absolute difference between actual and predicted values. Lower values are better.

Root Mean Squared Error (RMSE)

Measures prediction error while giving greater importance to larger errors. Lower values are better.

R² Score

Measures how much variation in the target variable is explained by the model. Higher values are generally better.

5. Model Performance Comparison

Model| MAE| RMSE| R² Score
Random Forest| 5.4459| 9.7942| 0.7942
Extra Trees| 5.4103| 9.5319| 0.8051
Gradient Boosting| 5.2251| 9.6021| 0.8022
Voting Regressor| 5.2299| 9.4931| 0.8067

6. Results and Analysis

The models produced different prediction performances.

- Gradient Boosting achieved the lowest MAE.
- Voting Regressor achieved the lowest RMSE.
- Voting Regressor achieved the highest R² score.

The Voting Regressor provided the best overall result based on RMSE and R², while Gradient Boosting produced the lowest average absolute error.

7. Unit 5 Conclusion

The regression task successfully compared four models for predicting the next heart rate value. Combining multiple models through a Voting Regressor produced strong overall performance.

---

Tools and Technologies Used

The project uses the following technologies:

Technology| Purpose
Python| Main programming language
Google Colab / Jupyter Notebook| Development and execution
Pandas| Data handling and manipulation
NumPy| Numerical operations
Matplotlib| Data visualization
Seaborn| Statistical visualization
Plotly| Interactive charts
Scikit-learn| Machine learning algorithms and evaluation
hmmlearn| Hidden Markov Model implementation
MLflow| Experiment tracking and model management
Excel| Dataset storage and preparation

MLflow Experiment Tracking

MLflow is used to track and organize machine learning experiments.

Its main components include:

- Experiment: A collection of related machine learning runs.
- Run: A single execution of a model or experiment.
- Parameters: Model settings and hyperparameters.
- Metrics: Evaluation results such as accuracy, MAE, RMSE, and R².
- Artifacts: Files, charts, reports, and other saved outputs.
- Models: Trained models saved for future use.

MLflow helps compare experiments, monitor model performance, and maintain a record of training configurations.

Project Workflow

1. Load the datasets.
2. Explore and understand the data.
3. Perform data visualization.
4. Clean and preprocess the data.
5. Select suitable machine learning algorithms.
6. Train the models.
7. Evaluate model performance.
8. Compare the results.
9. Perform sample predictions.
10. Track experiments using MLflow.

Overall Conclusion

This Machine Learning course project demonstrates the implementation of different machine learning techniques across two reviews.

Review 1 focuses on patient disease classification using Logistic Regression, Decision Tree, Random Forest, KNN, and SVM.

Review 2 explores unsupervised clustering, sequential modelling using Hidden Markov Models, and numerical prediction using regression algorithms.

The project provides practical experience in data preprocessing, visualization, model training, evaluation, comparison, prediction, and experiment tracking using Python and its machine learning libraries.

Note: The Review 1 classification dataset and Review 2 PhysioNet 2012 ICU dataset are separate. Their results and objectives should be considered independently.
