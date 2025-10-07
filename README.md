# 💰 Real-Time Loan Analytics Platform

A **real-time financial analytics dashboard** built using **Streamlit**, **MySQL**, and **Apache Kafka**.  
This platform provides **live loan insights**, interactive charts, and key performance metrics for loan management systems.

---

## 🚀 Project Overview

The **Real-Time Loan Analytics Platform** is designed to continuously track loan data streamed from a Kafka producer and consumed by a Kafka consumer.  
All data is updated dynamically in **real-time** and visualized on a modern Streamlit dashboard.

---

## 🎯 Key Features

- ⚡ **Real-time data streaming** from **Kafka → MySQL → Streamlit**
- 🧠 **Kafka Consumer Integration** for continuous live loan data updates
- 📊 **Interactive Visualizations** (Bar, Pie, Line charts) with Plotly
- 💳 **Live KPIs:** Total Loans, Approved, Pending, Average Loan Value
- 🏆 **Top Borrowers** ranked by Loan Amount
- 🔍 **Search & Filter** functionality for loan data
- 🎨 **Dark Mode UI** with Neon Highlights
- 🔄 **Auto-refresh every 10 seconds** (powered by `streamlit-autorefresh`)

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

## 🏗️ Project Structure

Real_Time_Loan_Analytics_Platform/
│
├── Loan_Analytics_Platform/
│ ├── loan_dashboard.py
│ ├── kafka_consumer.py
│ ├── database_config.py
│ └── utils/
│
├── assets/
│ ├── dashboard_header.png
│ ├── loan_amount_chart.png
│ ├── loan_count_pie.png
│ ├── top_borrowers.png
│ └── loan_table.png
│
├── requirements.txt
└── README.md

yaml
Copy code

---

## 🖼️ Dashboard Preview

### 🏠 Dashboard Header & KPIs  
Displays real-time KPIs: **Total Loans**, **Approved Loans**, **Pending Loans**, **Approval Rate**, and **Average Loan Amount**.

![Dashboard Header](assets/dashboard_header.png)

---

### 💵 Loan Amount by Status  
Interactive bar chart comparing total loan amounts by status (Approved / Pending).

![Loan Amount Chart](assets/loan_amount_chart.png)

---

### 🥧 Loan Count by Status  
Live pie chart showing the ratio of approved vs pending loans.

![Loan Count Pie](assets/loan_count_pie.png)

---

### 🏆 Top Borrowers  
List of borrowers with the highest loan amounts, updated in real-time.

![Top Borrowers](assets/top_borrowers.png)

---

### 📋 Loan Details Table  
Complete table of all loan records streamed via Kafka and stored in MySQL.

![Loan Table](assets/loan_table.png)

---

## ⚙️ How to Run the Project

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/<your-username>/Real_Time_Loan_Analytics_Platform.git
cd Real_Time_Loan_Analytics_Platform
2️⃣ Install Dependencies
bash
Copy code
pip install -r requirements.txt
3️⃣ Start Kafka & Zookeeper
bash
Copy code
zookeeper-server-start.bat config/zookeeper.properties
kafka-server-start.bat config/server.properties
4️⃣ Run Kafka Producer (to stream loan data)
bash
Copy code
python kafka_producer.py
5️⃣ Run Kafka Consumer (to push data into MySQL)
bash
Copy code
python kafka_consumer.py
6️⃣ Launch Streamlit Dashboard
bash
Copy code
streamlit run Loan_Analytics_Platform/loan_dashboard.py
📡 Real-Time Data Flow
Producer: Streams new loan applications into Kafka topics

Consumer: Reads those messages and inserts them into MySQL

Streamlit App: Fetches and visualizes the data live every few seconds

🧩 Future Enhancements
🔐 Add user authentication and role-based access

📈 Integrate more ML models for loan default prediction

☁️ Deploy using AWS (EC2, RDS, MSK) or Docker
