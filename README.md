# IntrusionDetectProxy
# Machine Learning-Driven Web Application Firewall (WAF)

This repository contains the implementation of a machine learning-based Web Application Firewall (WAF) designed to enhance web application security by detecting and mitigating potential threats in real-time. The project leverages BurpSuite for data collection, Python for data preprocessing, and machine learning algorithms for accurate threat detection and classification.


## Overview

This project integrates machine learning into a WAF system, leveraging algorithms to detect web application vulnerabilities in HTTP requests. It automates the analysis of intercepted HTTP traffic to identify common threats like SQL injection, XSS, CSRF, and more. 

---

## Methodology

### Data Collection with BurpSuite

- **BurpSuite Setup**: Configured to intercept HTTP traffic between users and the web server, capturing requests and responses for analysis.  
- **Log File Generation**: Stores intercepted HTTP traffic in structured log files.  

### Data Preprocessing

- **Log File Parsing**: Extracts key information such as request URLs, headers, and parameters from raw log files.  
- **HTTP Parameter Extraction**: Identifies and organizes parameters for machine learning.  

### Feature Engineering

- **Encoding Techniques**: Converts HTTP parameters into numerical representations using one-hot encoding, tokenization, or hashing.  
- **Feature Selection**: Selects relevant features for improved model performance.  

### Machine Learning Models

1. **Binary Classification**:  
   - **Purpose**: Identifies whether HTTP traffic contains intrusion signals.  
   - **Technique**: Random Forest Classifier.  

2. **Multiclass Classification**:  
   - **Purpose**: Classifies intrusion types (e.g., SQL injection, XSS).  
   - **Technique**: XGBoost Classifier.  

---

## System Design and Architecture

The WAF system consists of the following modules:  

1. **Data Collection Module**: Captures and logs HTTP traffic.  
2. **Data Preprocessing Module**: Parses log files and organizes data for feature engineering.  
3. **Machine Learning Module**: Classifies HTTP requests as benign or malicious.  
4. **Decision Engine**: Determines actions based on classification results (e.g., blocking malicious requests).  
5. **Response Mechanism**: Interacts with the web server to allow or block requests.  

---

## Data Analysis

- **Binary Classification**: Identified class imbalance in datasets with 81.9% non-intrusion signals.  
- **Multiclass Classification**: Observed variations in intrusion types across features like protocol type, service, and flag.  
- **Exploratory Data Analysis (EDA)**: Used PCA and t-SNE for visualization, revealing separability and overlap in data clusters.  

---

## Results and Conclusion

### Key Takeaways:

- **Effective Threat Mitigation**: Real-time detection and response to web threats.  
- **Improved Accuracy**: Reduced false positives and negatives.  
- **Challenges**: Handling imbalanced datasets, feature selection, and model interpretability.  

---

**Usage**
Configure BurpSuite to intercept HTTP traffic and generate log files.
Run the Python script for preprocessing and feature extraction:
python preprocess.py

Train the machine learning models or load pre-trained models for predictions:
python train_model.py

Deploy the WAF system using Flask:
python app.py

Access the application in your browser at http://localhost:8080.

**Acknowledgments**
This project uses BurpSuite for data collection and leverages machine learning libraries like scikit-learn and XGBoost for model implementation.
