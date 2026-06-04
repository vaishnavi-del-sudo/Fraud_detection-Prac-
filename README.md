**Financial Fraud Detection System**

An end-to-end Machine Learning project designed to detect fraudulent financial transactions. This project includes data exploration and analysis on highly imbalanced transaction data, model pipeline generation, and an interactive Streamlit web application for real-time predictions.

**📌 Project Overview**

Financial fraud costs institutions and individuals billions of dollars annually. This project utilizes an anonymized financial transaction dataset to flag suspicious activities based on transaction types, amounts, and account balance variations before and after a transaction occurs.

**The repository features:**

**analysis_model.ipynb**__: Data ingestion, structure verification, and exploratory data analysis (EDA).

**fraud_detection.py**__: A lightweight user interface built with Streamlit allowing end-users to input custom transaction vectors and receive instant fraud verdicts.

**📊 Dataset Insights During exploration** 

(analysis_model.ipynb), two primary data files were ingested:

_AIML Dataset.csv_: The primary operational dataframe (df2) containing 6,362,620 rows and 11 features.

Class Imbalance: Highly skewed data where only 0.13% of overall transactions are flagged as genuine fraud (isFraud = 1).

Missing Values: 0 null records, ensuring absolute data integrity for the engineering pipeline.

_DataSet.csv_: A wide secondary dataset (df1) featuring 3,925 features across 9,082 rows, showcasing an extensive number of null entities requiring strategic lookup alignment.

**⚙️ Features Used**

for PredictionThe Streamlit application leverages a pre-trained serialized model (fraud_detection_pipeline.pkl) that expects the following key features:

Feature Name Type Description type Categorical The method of transaction (CASH_OUT, PAYMENT, CASH_IN, TRANSFER, DEBIT) 


**🚀 Getting Started**

**1. Prerequisites**__

  Ensure you have Python 3.8+ installed.
  
  Install the necessary dependencies using pip:
  
_Bash_

   pip install streamlit, pandas, numpy, joblib, scikit-learn, matplotlib, seaborn
   
**2. Repository Structure Plain text**__

├── analysis_model.ipynb          # Jupyter notebook containing initial data EDA

├── fraud_detection.py            # Streamlit application script

├── fraud_detection_pipeline.pkl  # Trained ML pipeline (Saved Model)

└── README.md                     # Project Documentation

**3. Running the Web App**__

Make sure your serialized model (fraud_detection_pipeline.pkl) is in the same directory as fraud_detection.py.

Run the app locally via:

_Bash_


streamlit run fraud_detection.py

**🖥️ Application UI Guide**

Once launched, 

the Streamlit app offers an intuitive interface:

Input Fields: Select the transaction type from a dropdown menu and enter financial values (amounts and balances).

Prediction Core: Upon clicking the "Predict" button, the inputs are converted into a structured pandas.DataFrame matching the model's exact signature format.

Real-time Feedback:

🟢 If legitimate, a green success banner highlights a safe transaction.

🔴 If fraudulent, a red error banner warns the operator immediately.

Note: The underlying execution fetches the primary element of the array return object (model.predict(input_data)[0]) ensuring rapid single-vector inference.
