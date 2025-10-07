# 💫 Real-Time Loan Analytics Platform

A **real-time loan monitoring dashboard** built with **Streamlit**, **MySQL**, and **Apache Kafka**.  
This platform helps organizations visualize **live loan transactions**, monitor loan approvals, and analyze borrower patterns — all in **real time**.

---

## 📖 Overview

The **Real-Time Loan Analytics Platform** provides an end-to-end streaming architecture:
- **Kafka Producer** generates live loan event data  
- **Kafka Consumer** processes and inserts data into **MySQL**  
- **Streamlit Dashboard** visualizes live updates automatically  

The dashboard refreshes every few seconds to display the latest information without manual reloads.

---

## 🎯 Key Features

- ⚡ Real-time streaming from **Kafka → MySQL → Streamlit**
- 📊 Interactive **Plotly visualizations** (Bar, Pie, Line)
- 💳 **KPI metrics:** Total Loans, Approved, Pending, Average Value
- 🏆 **Top Borrowers** ranking with real-time updates
- 🔍 **Search & Filter** for granular insights
- 🎨 Modern dark theme with neon highlights
- 🔄 Auto-refresh every 10 seconds

---

## 🧱 Tech Stack

| Layer | Technology |
|--------|-------------|
| **Frontend** | Streamlit |
| **Visualization** | Plotly |
| **Backend** | Python (MySQL Connector, Kafka Consumer) |
| **Database** | MySQL |
| **Real-Time Source** | Apache Kafka |
| **Styling** | Custom Streamlit CSS |

---

## 🗄️ Data Flow Architecture

Kafka Producer → Kafka Consumer → MySQL Database → Streamlit Dashboard




## 🧠 Database Setup (MySQL)

Before running the app, create the database and table:

```sql
CREATE DATABASE loan_data;
USE loan_data;

CREATE TABLE loan_events (
    loan_id VARCHAR(255) PRIMARY KEY,
    user_id VARCHAR(255),
    amount DECIMAL(10,2),
    status VARCHAR(50),
    timestamp BIGINT
);


⚙️ Configuration Setup

Create a configuration file at:
Loan_Analytics_Platform/config/config.ini

[mysql]
host=localhost
database=loan_data
user=root
password=YOUR_MYSQL_PASSWORD



🧩 Installation & Running the Project
1️⃣ Clone the Repository
git clone https://github.com/<your-username>/Real_Time_Loan_Analytics_Platform.git
cd Real_Time_Loan_Analytics_Platform

2️⃣ Create & Activate Virtual Environment
python -m venv venv
venv\Scripts\activate     # For Windows

3️⃣ Install Dependencies
pip install -r requirements.txt

4️⃣ Start MySQL Server

Ensure your MySQL service is running and accessible.

5️⃣ Start Kafka and Zookeeper
zookeeper-server-start.bat config/zookeeper.properties
kafka-server-start.bat config/server.properties

6️⃣ Run Kafka Producer (optional for live data)
python Loan_Analytics_Platform/produce_test_events.py

7️⃣ Run Kafka Consumer
python Loan_Analytics_Platform/kafka_consumer.py

8️⃣ Launch Streamlit Dashboard
streamlit run Loan_Analytics_Platform/loan_dashboard.py

9️⃣ Open in Browser

Once Streamlit starts, open:
👉 http://localhost:8501
