AI-Powered Intrusion Detection System (IDS)

Overview

This project implements an AI-powered Intrusion Detection System (IDS) that leverages machine learning to detect malicious network traffic in real-time. The system captures network packets, extracts features, and classifies them using a pre-trained model. Alerts are generated when malicious traffic is detected, and a web interface is used to visualize the alerts.

The system is built using Python, scikit-learn, pcapy, and Flask, with a machine learning model trained on the KDD Cup 1999 dataset.

Features

Real-time network packet capture.

Feature extraction from network traffic.

Machine learning model (Random Forest) to classify traffic as benign or malicious.

Web interface to visualize and display alerts.

SQLite database to log detected threats.

Easily extendable with other machine learning models and threat intelligence sources.


Technologies Used

Python: Main programming language.

scikit-learn: For machine learning model building and evaluation.

pcapy: For real-time packet capture and analysis.

Flask: To create a web interface for alert visualization.

SQLite: To store logs and alerts.

Matplotlib/Plotly: For data visualization and reporting.


Requirements

Python 3.6+

Install required dependencies:

pip install scikit-learn pandas pcapy flask matplotlib plotly


Dataset

This project uses the KDD Cup 1999 dataset, which is widely used in intrusion detection research. You can download it from the UCI Machine Learning Repository. The dataset contains a variety of network traffic instances labeled as either normal or malicious.

Setup

1. Download the Dataset:

Download the KDD Cup 1999 dataset and place it in the project directory. The dataset should be in CSV format.



2. Train the Model:

Run the following script to train the machine learning model using the dataset:


python train_model.py

This will preprocess the data, train a Random Forest classifier, and save the trained model as intrusion_detection_model.pkl.


3. Run the Flask Web App:

Start the Flask web application to monitor alerts and visualize them in a browser:


python app.py


4. Run the Packet Capture Script:

Capture live network packets and classify them in real-time:


python capture_intrusions.py

This script will continuously monitor network traffic and use the trained model to classify each packet as either benign or malicious. If malicious activity is detected, an alert will be logged in the SQLite database.



Usage

1. Open a web browser and navigate to http://localhost:5000 to view the AI-Powered IDS dashboard.


2. The dashboard will show the most recent alerts with timestamps and alert messages.


3. The real-time packet capture script will continuously monitor the network for suspicious activity and log alerts.



Example of Output

Alert Message: "Malicious packet detected!"

Timestamp: The date and time when the malicious packet was detected.


Sample Web Interface:

Customization & Extensions

1. Use Deep Learning Models:

You can replace the Random Forest classifier with deep learning models like Convolutional Neural Networks (CNNs) or Long Short-Term Memory (LSTM) networks to improve detection accuracy for complex attack patterns.



2. Integration with Threat Intelligence:

Integrate threat intelligence feeds (e.g., STIX, TAXII) to enhance detection by correlating known attack patterns with the live traffic data.



3. Enhance Feature Extraction:

Extend the feature extraction pipeline to include more advanced network flow statistics or detailed packet analysis.



4. Incident Response:

You can automate response actions based on detected attacks, such as blocking malicious IPs or triggering alerts in other security systems (SIEMs).




Future Improvements

Real-time model retraining: Continuously update the machine learning model with new data to detect new attack patterns.

Integration with other security tools: Integrate the IDS with firewalls, SIEM systems, and endpoint protection tools for enhanced protection.

Distributed IDS: Extend the system to work in a distributed network environment, improving scalability and detection across different network segments.


License

This project is licensed under the MIT License - see the LICENSE file for details.


---


