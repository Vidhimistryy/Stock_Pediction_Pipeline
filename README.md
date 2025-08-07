## 📈 Stock Price Prediction Pipeline using AWS S3, Glue, Athena, Google Colab, and Power BI
This project demonstrates a cloud-integrated machine learning pipeline that forecasts Apple Inc. (AAPL) stock prices using an LSTM model. It leverages AWS services for data storage and cataloging, Google Colab for model training, and Power BI for visualization.

## ✅ Project Overview
⏳ Data: Historical AAPL stock data (aaplcsv.csv)

🪣 Storage: Amazon S3 bucket

🛡️ Access: AWS IAM role with S3 and Glue permissions

🧪 ETL: AWS Glue Crawler to create table in Glue Data Catalog

🔎 Querying: AWS Athena to explore and export data

🤖 Modeling: LSTM time-series forecasting in Google Colab

📊 Visualization: Interactive Power BI dashboard

## 📁 Dataset Details
File: aaplcsv.csv

Source: Historical data from Yahoo Finance

Fields: Date, Open, High, Low, Close, Adj Close, Volume

Stored in: s3://vidhi_stockvision_data/aaplcsv.csv

## 🛠️ AWS Configuration
🔐 IAM Role
Created IAM role with policies:

AmazonS3FullAccess

AWSGlueServiceRole


🪣 S3 Bucket
Uploaded aaplcsv.csv to S3

Folder path: s3://your-bucket-name/aaplcsv.csv

🧬 AWS Glue
Created a Crawler to scan the S3 path

Generated a Glue table named aaplcsv in database stockvision_db

🔎 Athena Query (Query Editor v2)
sql
Copy
Edit
SELECT * FROM stockvision_db.aaplcsv
ORDER BY date ASC
LIMIT 10;
Ensured data is chronologically ordered for time-series modeling

Previewed data to validate Glue schema

Exported output as CSV for model training

🤖 LSTM Model Training in Google Colab
Loaded and normalized Close price data

Split into training and test sets

Created sequences using a 60-day sliding window

Trained an LSTM model using TensorFlow/Keras

📊 Power BI Dashboard
Created a Power BI report with:

📈 Actual vs Predicted Close Prices (Line Chart)

📉 Moving Average Trends

📊 Daily Volume Analysis

✅ Interactive filters by Date Range

🔗 (Add screenshots or .pbix download link here)

## 📦 Project Structure
graphql
Copy
Edit
├── data/
│   └── aaplcsv.csv                # Raw data from Yahoo Finance
├── colab_notebooks/
│   └── stock_lstm_model.ipynb     # LSTM training and predictions
├── powerbi/
│   └── aapl_dashboard.pbix        # Power BI report file
├── aws/
│   ├── glue_crawler_config.txt    # Crawler settings
│   └── athena_query.sql           # SQL scripts
└── README.md                      # Project overview

## 🎯 Key Takeaways
🔗 Seamless integration of AWS S3, Glue, and Athena

🔁 End-to-end ETL + ML + BI workflow

📡 Scalable and modular pipeline

📚 Strong demonstration of cloud + data science skills

## 👩‍💻 Author
Vidhi Mistry
vidhimistry292@gmail.com

## 📄 License
This project is released under the MIT License.



