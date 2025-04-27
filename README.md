# Overview

This project focuses on detecting network intrusions using machine learning techniques. Our main goal was to accurately classify activities based on network features using a Random Forest Classifier.The system aims to automatically detect unusual activities or attacks in a network and differentiate them from normal traffic.This is a critical task for maintaining the security and integrity of computer networks, especially in environments where cyber threats are frequent.

# Objective

The objective of project is to build network intrusion detection system to detect anomalies and attacks in the network. 

There are two problems: 
- Binomial classification: Detect anomalies by predicting Activity is normal or attack.
- Multinomial Classification: Detecting type of activity by predicting Activity is Normal or Back or Buffer Over flow or FTP Write or Guess Password or Neptune or N-Map or Port Sweep or Root Kit or Satan or Smurf.

### Table of Contents

Data

Usage

Methodology

Models Used

Evaluation Metrics

Results

Conclusion

### Data

Tables: There are 10 tables for different type of attacks with same columns 
a. Data_of_Attack_Back_Normal  
b. Data_of_Attack_Back  
c. Data_of_Attack_Back_BufferOverflow 
d. Data_of_Attack_Back_FTPWrite 
e. Data_of_Attack_Back_GuessPassword 
f. Data_of_Attack_Back_Neptune 
g. Data_of_Attack_Back_NMap 
h. Data_of_Attack_Back_PortSweep 
i. Data_of_Attack_Back_RootKit 
j. Data_of_Attack_Back_Satan 
k. Data_of_Attack_Back_Smurf 

BASIC FEATURES OF EACH NETWORK CONNECTION VECTOR 
1 Duration:  Length of time duration of the connection 
2 Protocol_type: Protocol used in the connection 
3 Service: Destination network service used 
4 Flag: Status of the connection – Normal or Error 
5 Src_bytes: Numberof data bytes transferred from source to destination in single connection 
6 Dst_bytes: Numberof data bytes transferred from destination to source in single connection 
7 Land: if source and destination IP addresses and port numbers are equal then, this variable 
takes value 1 else 0 
8 Wrong_fragment: Total numberof wrong fragments in this connection 
9 Urgent: Numberof urgent packets in this connection. Urgent packets are packets with the 
urgent bit activated 
CONTENT RELATED FEATURES OF EACH NETWORK CONNECTION VECTOR 
10 Hot: Numberof „hot‟ indicators in the content such as: entering a system directory, creating 
programs and executing programs 
11 Num_failed _logins: Count of failed login attempts 
12 Logged_in Login Status: 1 if successfully logged in; 0 otherwise  
13  Num_compromised: Number of ``compromised'' conditions  
14 Root_shell: 1 if root shell is obtained; 0 otherwise 
15 Su_attempted: 1 if ``su root'' command attempted orused; 0 otherwise 
16 Num_root: Number of ``root'' accesses or numberof operations performed as a root in the 
connection 
17 Num_file_creations: Number of file creation operations in the connection 
18 Num_shells: Number of shell prompts 
19 Num_access_files: Number of operations on access control files 
20 Num_outbound_cmds: Number of outbound commands in an ftp session   
21 Is_hot_login: 1 if the login belongs to the ``hot'' list i.e., root or admin; else 0  
22 Is_guest_login: 1 if the login is a ``guest'' login; 0 otherwise 
 
TIME RELATED TRAFFIC FEATURES OF EACH NETWORKCONNECTION VECTOR 
23 Count: Numberof connections to the same destination host as the current connection in the past two seconds 
24 Srv_count: Numberof connections to the same service (port number) as the current connection in the past two seconds 
25 Serror_rate: The percentage of connections that have activated the flag (4) s0, s1, s2 or s3, among the connections aggregated in count (23) 
26 Srv_serror_rate: The percentage of connections that have activated the flag (4) s0, s1, s2 or s3, among the connections aggregated in srv_count (24) 
27 Rerror_rate: The percentage of connections that have activated the flag (4) REJ, among the connections aggregated in count (23) 
28 Srv_rerror_rate: The percentage of connections that have activated the flag (4) REJ, among the connections aggregated in srv_count (24) 
29 Same_srv_rate: The percentage of connections that were to the same service, among the connections aggregated in count (23) 
30 Diff_srv_rate: The percentage of connections that were to different services, among the connections aggregated in count (23) 
31 Srv_diff_host_ rate: The percentage of connections that were to different destination machines among the connections aggregated in srv_count (24) 

HOST BASED TRAFFIC FEATURES IN A NETWORK CONNECTION VECTOR 
32 Dst_host_count: Numberof connections having the same destination host IP address 
33 Dst_host_srv_ count: Numberof connections having the same port number 
34 Dst_host_same _srv_rate: The percentage of connections that were to the same service, among the connections aggregated in dst_host_count (32) 
35 Dst_host_diff_ srv_rate: The percentage of connections that were to different services, among the connections aggregated in dst_host_count (32) 
36 Dst_host_same _src_port_rate:  The percentage of connections that were to the same source port, among the connections aggregated in dst_host_srv_count (33) 
37 Dst_host_srv_ diff_host_rate: The percentage of connections that were to different destination machines, among the connections aggregated in dst_host_srv_count (33) 
38 Dst_host_serro r_rate: The percentage of connections that have activated the flag (4) s0, s1, s2 or s3, among the connections aggregated in dst_host_count (32) 
39 Dst_host_srv_s error_rate: The percent of connections that have activated the flag (4) s0, s1, s2 or s3, among the connections aggregated in dst_host_srv_count (33) 
40 Dst_host_rerror_rate: The percentage of connections that have activated the flag (4) REJ, among the connections aggregated in dst_host_count (32) 
41 Dst_host_srv_rerror_rate: The percentage of connections that have activated the flag (4) REJ, among the connections aggregated in dst_host_srv_count (33) 
 
Type Features: 
Nominal:  Protocol_type(2), Service(3), Flag(4) 
Binary: Land(7), logged_in(12), root_shell(14), su_attempted(15), is_host_login(21), 
is_guest_login(22) 
Numeric: Duration(1), src_bytes(5), dst_bytes(6), wrong_fragment(8), urgent(9), hot(10), 
num_failed_logins(11), num_compromised(13), num_root(16), num_file_creations(17), 
num_shells(18), num_access_files(19), num_outbound_cmds(20), count(23), srv_count(24), 
error_rate(25), srv_serror_rate(26),  rerror_rate(27),srv_rerror_rate(28),  same_srv_rate(29), 
diff_srv_rate(30), srv_diff_host_rate(31), dst_host_count(32), dst_host_srv_count(33), 
dst_host_same_srv_rate(34), dst_host_diff_srv_rate(35),  dst_host_same_src_port_rate(36),  
dst_host_srv_diff_host_rate(37), dst_host_serror_rate(38),  dst_host_srv_serror_rate(39),  
dst_host_rerror_rate(40), dst_host_srv_rerror_rate(41)



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

     0 → Normal

     1 → Attack
     
  - b. Multinomial:
  
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


#### Future Work
- Try advanced ensemble methods like XGBoost or LightGBM.

- Handle class imbalance (if needed) using SMOTE or class_weight.

- Tune hyperparameters using GridSearchCV for further optimization.
    
