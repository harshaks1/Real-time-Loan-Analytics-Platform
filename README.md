# 💫 Real-Time Loan Analytics Dashboard

## 📘 Project Description
The **Real-Time Loan Analytics Dashboard** is a Streamlit-based web application designed to visualize **live loan event data** from **Kafka → MySQL → Streamlit** in real time.  

It allows teams to monitor and analyze key metrics such as **total loans**, **approved and pending loans**, **average loan amount**, and **top borrowers**.  
The system automatically refreshes every few seconds, ensuring users always see the most up-to-date loan activity.

---

## 🎯 Key Features
- ⚡ Real-time loan data integration from MySQL  
- 📊 Interactive visualizations using Plotly (Bar, Pie, and Line charts)  
- 💳 KPI metrics (Total Loans, Approved, Pending, Average Loan Amount, etc.)  
- 🏆 Top borrowers ranked by loan amount  
- 🔍 Search and filter functionality for detailed loan data  
- 🎨 Sleek dark theme with neon accents  
- 🔄 Auto-refresh every 10 seconds for live updates  

---

## 🧠 Tech Stack

| Layer | Technology Used |
|--------|------------------|
| Frontend | Streamlit |
| Visualization | Plotly |
| Backend | Python (MySQL Connector) |
| Database | MySQL |
| Real-Time Data Source | Kafka (optional) |
| Styling | Custom CSS inside Streamlit |

---

## ⚙️ Project Requirements

### 🧰 Software Requirements
- **Python** 3.10 or above  
- **MySQL Server** 8.0 or above  
- **Kafka** (optional, for streaming simulation)  
- **VS Code / PyCharm** (for local development)

### 🧩 Python Libraries
Install the following packages:

```bash
pip install streamlit pandas mysql-connector-python plotly streamlit-autorefresh numpy
(Optional but recommended):

bash
Copy code
pip install python-dotenv openpyxl requests
🗄️ Database Setup (MySQL)
Open MySQL Command Line or MySQL Workbench.

Create the database:


CREATE DATABASE loan_data;
USE loan_data;
Create the loan_events table:


CREATE TABLE loan_events (
    loan_id VARCHAR(255) PRIMARY KEY,
    user_id VARCHAR(255),
    amount DECIMAL(10,2),
    status VARCHAR(50),
    timestamp BIGINT
);
Insert some sample data:

sql
Copy code
INSERT INTO loan_events VALUES
('0001fd51-d74b-4b2d-9b05-dc4a56eac4cc','48246252-b839-4c3a-a877-6897a91edcb6',8033.79,'approved',1759488782),
('000f328b-b57f-4bcf-8afa-a04858f1d934','c240cac8-ae91-4018-9a31-a764d066dd44',18220.50,'pending',1759488758);
⚙️ Configuration Setup
Create a configuration file for your MySQL credentials:
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
bash
Copy code
Real_Time_Loan_Analytics_Platform/
├── Loan_Analytics_Platform/
│   ├── loan_dashboard.py            # Main Streamlit app
│   ├── config/
│   │   └── config.ini               # MySQL credentials
│   ├── __init__.py
│   ├── kafka_consumer.py            # (optional) Kafka consumer script
│   └── produce_test_events.py       # (optional) Data producer
├── venv_streamlit/                  # Virtual environment
├── README.md
└── requirements.txt
🚀 How to Run the Project Locally
Step 1: Open your project
bash
Copy code
cd D:\Real_Time_Loan_Analytics_Platform\Loan_Analytics_Platform
Step 2: Activate the virtual environment
powershell
Copy code
D:\Real_Time_Loan_Analytics_Platform\venv_streamlit\Scripts\Activate.ps1
Step 3: Install dependencies
bash
Copy code
pip install -r requirements.txt
Step 4: Verify MySQL connection
Ensure your MySQL server is running and the loan_data database exists.

Step 5: Run the Streamlit dashboard
bash
Copy code
streamlit run loan_dashboard.py
Step 6: Open in your browser
Once Streamlit launches, open:

arduino
Copy code
http://localhost:8501
🧮 Dashboard Outputs
📊 Dashboard Header and KPIs
Displays total loans, approved loans, pending loans, approval rate, and average loan amount.
📸 [Insert Screenshot: Dashboard Header]

💵 Loan Amount by Status
Interactive bar chart comparing total loan amounts by approval status.
📸 [Insert Screenshot: Loan Amount Chart]

🥧 Loan Count by Status
Pie chart showing the proportion of approved vs. pending loans.
📸 [Insert Screenshot: Loan Count Pie Chart]

📈 Average Loan Trend
Line chart showing variations in average loan amounts over time.
📸 [Insert Screenshot: Loan Trend Chart]

🏆 Top Borrowers Table
List of top 5 borrowers based on loan amount.
📸 [Insert Screenshot: Top Borrowers Table]

📋 Detailed Loan Data
Searchable and filterable table for all loan entries.
📸 [Insert Screenshot: Loan Data Table]
