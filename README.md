# Overview

This project focuses on detecting network intrusions using machine learning techniques. Our main goal is to accurately classify activities based on network features using a Random Forest Classifier.The system aims to automatically detect unusual activities or attacks in a network and differentiate them from normal traffic.This is a critical task for maintaining the security and integrity of computer networks, especially in environments where cyber threats are frequent.

# Objective

The objective of project is to build network intrusion detection system to detect anomalies and attacks in the network. 

There are two problems: 
- Binomial classification: Detect anomalies by predicting Activity is normal or attack.
- Multinomial Classification: Detecting type of activity by predicting Activity is Normal or Back or Buffer Over flow or FTP Write or Guess Password or Neptune or N-Map or Port Sweep or Root Kit or Satan or Smurf.

### Table of Contents

- Data
- Usage
- Methodology
- Models Used
- Evaluation Metrics
- Results
- Conclusion

### Data

Tables: There are 10 tables for different type of attacks with same columns 
- Data_of_Attack_Back_Normal
- Data_of_Attack_Back
- Data_of_Attack_Back_BufferOverflow
- Data_of_Attack_Back_FTPWrite
- Data_of_Attack_Back_GuessPassword
- Data_of_Attack_Back_Neptune
- Data_of_Attack_Back_NMap
- Data_of_Attack_Back_PortSweep
- Data_of_Attack_Back_RootKit
- Data_of_Attack_Back_Satan
- Data_of_Attack_Back_Smurf 


### Usage

- Language: Python
- Libraries: scikit-learn, pandas, numpy
- Model Used: Random Forest Classifier
- Evaluation Metrics: Accuracy, Precision, Recall, F1-Score, ROC-AUC, Confusion Matrix

### Steps Involved

- Data Preparation
- Features selection.
- A target variable attack_class was created in two different ways:
   - a. Binomial:
       - 0 → Normal
       - 1 → Attack
     
  - b. Multinomial:
       - Normal
       - Back
       - Buffer Overflow
       - FTP Write
       - Guess Password
       - Neptune
       - Nmap
       - Port Sweep
       - Rootkit
       - Satan
       - Smurf


#### Future Work
- Try advanced ensemble methods like XGBoost or LightGBM.

- Handle class imbalance (if needed) using SMOTE or class_weight.

- Tune hyperparameters using GridSearchCV for further optimization.
    
