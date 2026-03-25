📘 Bayesian Classification for Fault Detection in Industrial Machinery

This project implements a Gaussian Naive Bayes classifier to detect faults in industrial machinery using the AI4I Predictive Maintenance Dataset.
The goal is to build a lightweight, fast, and interpretable fault detection system suitable for real-time industrial deployment, including a live simulation on new machine sensor readings.

🚀 Project Overview

Industrial machines generate large amounts of sensor data such as:

Air temperature

Process temperature

Rotational speed

Torque

Tool wear

Machine type

The objective is to use these sensor readings to determine whether a machine is:

Healthy (0)

Faulty (1)

Using Bayesian Classification, the project performs:

Data preprocessing

Feature encoding

Feature scaling

Training/testing split

Model training (Naive Bayes)

Evaluation (Accuracy, Confusion Matrix, Classification Report)

Real-time simulation on unseen machine data

Visualization dashboard


🛠 Technologies & Libraries Used
Core Libraries

Python 3.10+

pandas

numpy

seaborn

matplotlib

plotly

Machine Learning

scikit-learn

GaussianNB

LabelEncoder

train_test_split

StandardScaler

accuracy_score

classification_report

confusion_matrix

📊 Workflow Summary
1️⃣ Data Preprocessing

Removed irrelevant columns (UDI, Product ID)

Encoded categorical features (Type)

Split dataset into 70% training, 30% testing

Applied standard scaling for consistent feature ranges

2️⃣ Model Training (Gaussian Naive Bayes)

The Naive Bayes classifier was chosen because:

It is extremely fast

Works well with sensor noise

Provides probabilistic outputs

Suitable for real-time/edge device deployment

nb_model = GaussianNB()
nb_model.fit(X_train, y_train)

3️⃣ Model Evaluation
Metric	Result
Accuracy	0.958 (95.8%)
Precision (class 1)	0.37
Recall (class 1)	0.25
F1-score (class 1)	0.29
Confusion Matrix
[[2849   45]
 [  80   26]]


The model performs excellently for healthy machines, but fault detection can be improved by threshold tuning.

4️⃣ Real-Time Fault Detection Simulation

A custom simulation was created to mimic industrial monitoring.

✔ Reads 20 new unseen machine readings
✔ Encodes & scales data
✔ Predicts fault probability
✔ Applies adjustable threshold
✔ Prints each machine’s status line-by-line

Example Output:

Machine 02 | P(Fault): 0.018 → ⚠️ FAULT DETECTED
Machine 06 | P(Fault): 0.011 → ⚠️ FAULT DETECTED


Finally, results are saved to:

fault_detection_results.csv

5️⃣ Visualization Dashboard

Two clear visualizations:

✅ Machine Health Summary

A bar chart showing total Healthy vs Faulty machines.

✅ Fault Probability Scatter Plot

Shows each machine’s predicted probability and fault category.

These visuals help explain the simulation output during presentations.

🧠 Key Features

✔ Clean & interpretable Bayesian model

✔ Real industrial dataset (10,000+ rows)

✔ Live simulation on new raw sensor data

✔ Adjustable sensitivity threshold

✔ Professional visualization dashboard

✔ Ready for deployment on low-power devices

🏁 Conclusion

This project demonstrates that Gaussian Naive Bayes is an effective method for early fault detection in industrial machinery due to its:

Speed

Simplicity

Robustness to noise

Probabilistic decision-making

Real-time prediction capability

It provides a strong baseline for predictive maintenance systems and can be integrated into industrial monitoring pipelines.

📌 Future Enhancements

Improve recall using:

Bayesian Networks

Threshold optimization

SMOTE oversampling

Deploy model on edge/IoT devices

Connect to live streaming sensor data (MQTT / Kafka)

Build a dashboard interface (Streamlit)