# Overview

This project focuses on detecting network intrusions using machine learning techniques. Our main goal was to accurately classify activities based on network features using a Random Forest Classifier.
 We solved two different classification problems:

- Binomial Classification: Predict whether a network activity is Normal or Attack.

- Multinomial Classification: Predict the specific type of attack (e.g., Back, Neptune, Smurf) or Normal activity.

# Objective

The objective of project is to build network intrusion detection system to detect anomalies and attacks in the network. 

There are two problems: 
- Binomial classification: Detect anomalies by predicting Activity is normal or attack.
- Multinomial Classification: Detecting type of activity by predicting Activity is Normal or Back or Buffer Over flow or FTP Write or Guess Password or Neptune or N-Map or Port Sweep or Root Kit or Satan or Smurf.

### Project Setup
- Language: Python
- Libraries: scikit-learn, pandas, numpy
- Model Used: Random Forest Classifier
- Evaluation Metrics: Accuracy, Precision, Recall, F1-Score, ROC-AUC, Confusion Matrix

### Steps Involved

- Data Preparation
- Features selection.
- A target variable attack_class was created in two different ways:
   a. Binomial:
  0 → Normal
  1 → Attack
  b. Multinomial:
  Normal
  Back

Buffer Overflow

FTP Write

Guess Password

Neptune

Nmap

Port Sweep

Rootkit

Satan

Smurf
