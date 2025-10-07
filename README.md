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

yaml
Copy code

---

## 📁 Project Structure

Real_Time_Loan_Analytics_Platform/
│
├── Loan_Analytics_Platform/
│ ├── loan_dashboard.py # Main Streamlit App
│ ├── kafka_consumer.py # Kafka Consumer Script
│ ├── produce_test_events.py # Optional Kafka Producer Script
│ ├── config/
│ │ └── config.ini # MySQL Configuration
│ └── init.py
│
├── assets/ # Dashboard Images
│ ├── dashboard_header.png
│ ├── loan_amount_chart.png
│ ├── loan_count_pie.png
│ ├── top_borrowers.png
│ └── loan_table.png
│
├── requirements.txt
└── README.md

sql
Copy code

> ⚠️ **Note:** Ensure your images are located inside the `assets/` folder in the same directory as your `README.md`.

---

## 🧠 Database Setup (MySQL)

Create the database and table before running the app:

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
Insert sample data:

sql
Copy code
INSERT INTO loan_events VALUES
('0001fd51-d74b-4b2d-9b05-dc4a56eac4cc','48246252-b839-4c3a-a877-6897a91edcb6',8033.79,'approved',1759488782),
('000f328b-b57f-4bcf-8afa-a04858f1d934','c240cac8-ae91-4018-9a31-a764d066dd44',18220.50,'pending',1759488758);
⚙️ Configuration Setup
Create a configuration file at:
Loan_Analytics_Platform/config/config.ini

ini
Copy code
[mysql]
host=localhost
database=loan_data
user=root
password=YOUR_MYSQL_PASSWORD
🧩 Installation & Running the Project
1️⃣ Clone the Repository
bash
Copy code
git clone https://github.com/<your-username>/Real_Time_Loan_Analytics_Platform.git
cd Real_Time_Loan_Analytics_Platform
2️⃣ Create & Activate Virtual Environment
bash
Copy code
python -m venv venv
venv\Scripts\activate     # For Windows
3️⃣ Install Dependencies
bash
Copy code
pip install -r requirements.txt
4️⃣ Start MySQL Server
Ensure MySQL is running and accessible.

5️⃣ Start Kafka and Zookeeper
bash
Copy code
zookeeper-server-start.bat config/zookeeper.properties
kafka-server-start.bat config/server.properties
6️⃣ Run Kafka Producer (optional for live data)
bash
Copy code
python Loan_Analytics_Platform/produce_test_events.py
7️⃣ Run Kafka Consumer
bash
Copy code
python Loan_Analytics_Platform/kafka_consumer.py
8️⃣ Launch Streamlit Dashboard
bash
Copy code
streamlit run Loan_Analytics_Platform/loan_dashboard.py
9️⃣ Open in Browser
Once Streamlit starts, visit:
👉 http://localhost:8501
