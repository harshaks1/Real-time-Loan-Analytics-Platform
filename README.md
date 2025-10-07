# 💫 Real-Time Loan Analytics Dashboard

## 📘 Project Description
The **Real-Time Loan Analytics Dashboard** is a Streamlit-based web application designed to visualize **live loan event data** from **Kafka → MySQL → Streamlit** in real time.  
It allows organizations to track loan activities, monitor approvals, analyze borrower trends, and make data-driven decisions using live updates from the backend.

The system auto-refreshes every few seconds to reflect the latest loan transactions, eliminating the need for manual refresh and ensuring users always see current data.

---

## 🎯 Key Features
- ⚡ Real-time data streaming from MySQL  
- 📊 Interactive analytics using Plotly (Bar, Pie, and Line charts)  
- 💳 KPI metrics showing Total Loans, Approved, Pending, and Average Loan Value  
- 🏆 Top borrowers ranking based on loan amounts  
- 🔍 Search and filter functionality for granular insights  
- 🎨 Modern dark theme with neon highlights for readability  
- 🔄 Auto-refresh every 10 seconds for real-time data updates  

---

## 🧠 Tech Stack

| Layer | Technology |
|--------|-------------|
| Frontend | Streamlit |
| Visualization | Plotly |
| Backend | Python (MySQL Connector) |
| Database | MySQL |
| Real-Time Data Source | Kafka (optional) |
| Styling | Custom CSS in Streamlit |

---

## ⚙️ Project Requirements

### 🧰 Software Requirements
- **Python** 3.10 or higher  
- **MySQL Server** 8.0 or above  
- **Kafka** *(optional for simulation)*  
- **VS Code / PyCharm** (IDE for local development)

### 🧩 Python Libraries
Install all required dependencies:
```bash
pip install streamlit pandas mysql-connector-python plotly streamlit-autorefresh numpy
Optional (recommended):

bash
Copy code
pip install python-dotenv openpyxl requests
🗄️ Database Setup (MySQL)
Create the Database and Table

sql
Copy code
CREATE DATABASE loan_data;
USE loan_data;

CREATE TABLE loan_events (
    loan_id VARCHAR(255) PRIMARY KEY,
    user_id VARCHAR(255),
    amount DECIMAL(10,2),
    status VARCHAR(50),
    timestamp BIGINT
);
Insert Sample Data

sql
Copy code
INSERT INTO loan_events VALUES
('0001fd51-d74b-4b2d-9b05-dc4a56eac4cc','48246252-b839-4c3a-a877-6897a91edcb6',8033.79,'approved',1759488782),
('000f328b-b57f-4bcf-8afa-a04858f1d934','c240cac8-ae91-4018-9a31-a764d066dd44',18220.50,'pending',1759488758);
⚙️ Configuration Setup
Create a configuration file with your MySQL credentials.

Path:

arduino
Copy code
D:\Real_Time_Loan_Analytics_Platform\Loan_Analytics_Platform\config\config.ini
Content:

ini
Copy code
[mysql]
host=localhost
database=loan_data
user=root
password=YOUR_MYSQL_PASSWORD
📁 Project Structure
arduino
Copy code
Real_Time_Loan_Analytics_Platform/
├── Loan_Analytics_Platform/
│   ├── loan_dashboard.py            # Main Streamlit app
│   ├── config/
│   │   └── config.ini               # MySQL credentials
│   ├── __init__.py
│   ├── kafka_consumer.py            # (optional)
│   └── produce_test_events.py       # (optional)
├── assets/
│   ├── dashboard_header.png
│   ├── loan_amount_chart.png
│   ├── loan_count_pie.png
│   ├── top_borrowers.png
│   └── loan_table.png
├── README.md
└── requirements.txt
🚀 How to Run the Project Locally
Step 1: Open the Project
bash
Copy code
cd D:\Real_Time_Loan_Analytics_Platform\Loan_Analytics_Platform
Step 2: Activate Virtual Environment
powershell
Copy code
D:\Real_Time_Loan_Analytics_Platform\venv_streamlit\Scripts\Activate.ps1
Step 3: Install Dependencies
bash
Copy code
pip install -r requirements.txt
Step 4: Verify Database Connection
Ensure MySQL is running and the loan_data database is correctly configured.

Step 5: Run the Streamlit Application
bash
Copy code
streamlit run loan_dashboard.py
Step 6: Open in Browser
Once Streamlit starts, open:
👉 http://localhost:8501

🧮 Dashboard Outputs
📊 1️⃣ Dashboard Header and KPIs
Displays the total loans, approved loans, pending loans, approval rate, and average loan amount.
These metrics update automatically every few seconds.

![Dashboard Header](assets/dashboard_header.png)
Figure 1: Real-Time Loan Dashboard Header displaying live KPIs.

💵 2️⃣ Loan Amount by Status
An interactive bar chart comparing total loan amounts by their current approval status (Approved / Pending).

![Loan Amount Chart](assets/loan_amount_chart.png)  
Figure 2: Loan Amount Distribution by Status.

🥧 3️⃣ Loan Count by Status
A live pie chart representing the ratio of approved and pending loans.

![Loan Count Pie](assets/loan_count_pie.png)
Figure 3: Percentage breakdown of loan statuses.

🏆 4️⃣ Top Borrowers
A ranked list of the top 5 borrowers based on loan amount, helping identify high-value customers.

![Top Borrowers](assets/top_borrowers.png) 
Figure 4: Top Borrowers by Loan Amount.

📋 5️⃣ Detailed Loan Data Table
A searchable and filterable table that allows users to view all loan records in real time.

![Loan Table](assets/loan_table.png)
Figure 5: Detailed Loan Data Table with filtering options.
