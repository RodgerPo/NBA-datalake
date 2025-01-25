# AWS Data Lake Automation

## **Project Overview**
In this project, we automated the creation of a data lake in the cloud utilizing the S3, Glue, and Athena AWS services to ingest, store, and analyze the data. While this project uses NBA data, it can be repurposed to enhance processes across analytics, data pipelines, datasets, and reporting across any industry by simply swapping the data sources and schemas defined in Glue.

## Technologies Used
- **AWS S3**
- **AWS Glue**
- **AWS Athena**
- **AWS CloudShell**
- **SportsData.io API**
- **Python AWS SDK (Boto3)**

---

## **Technical Architecture**
![nba_API](https://s7.gifyu.com/images/Se8Qe.gif){width=250}
 1. The script starts off by creating an S3 bucket
 2. Then it creates a glue database
 3. Now we fetch the raw data from the API 
 4. Convert it to JSON and store it in our bucket
 5. Manually create the table in Glue with a specified schema pointing to the S3 bucket
 6. Configure Athena to use the Glue tables and database

---

## Key Features
- Automated data lake creation with a script that deploys S3 buckets, Glue databases, and Athena tables.
- API integration that can ingest real-time or historical data.
- A query-ready structure that includes pre-configured tables for analytics.
- Modular design that can be used across various use cases.

---

## How to Get Started

### **1. Clone the Repository**
```bash
git clone https://github.com/alahl1/NBADataLake.git  
cd NBADataLake
```
### **2. Configure Credentials**
- Grab your SportsData API Key
- Add the API key to the .env file and reference it in the Python script
- (Not Recommended) Store the key in the file itself to run the script in the AWS console

### **3. Run the Script**
- Open AWS CloudShell and create the setup_nba_data_lake.py file
- Copy the contents of the code into this new file using Nano or vim and save
```bash
python3 setup_nba_data_lake.py
```

### **Test the System**
1. Navigate to Athena in the AWS Console
2. In the editor, ensure you have the correct data selected
3. In the Query window, write your SQL command
```sql
SELECT firstname, lastname, points
FROM nba_players
```
4. Press the Run button and see the results listed below


### **Future Enhancements**
1. Fetch and sort players based on their PPG
2. Include fantasy points and projections
3. Combine with day 2 project to send automated fantasy news reports
