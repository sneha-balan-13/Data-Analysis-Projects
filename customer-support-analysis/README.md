# 🧠 Customer Support Ticket Prioritization with AI, SQL, Power BI, and Power Automate

This end-to-end project demonstrates how to classify and monitor customer support tickets using a combination of **Natural Language Processing**, **Machine Learning**, **Power BI**, and **Power Automate**.

---

## 📁 Project Structure

```
customer-support-analysis/
│
├── data/                     # Raw + cleaned datasets (CSV, DB)
│   ├── customer_tickets.db
|   ├── predicted_support_tickets.csv
|   └── support_tickets_cleaned.csv
├── notebooks/                # Python notebooks
│   ├── 01_data_cleaning.ipynb
│   ├── 02_priority_classifier.ipynb
│   └── 03_sql_upload.ipynb
├── sql/                      # SQL schema and queries
│   └── create_support_tickets.sql
├── powerbi/                  # Power BI reports
│   └── predicted_tickets_dashboard.pbix
├── powerautomate/            # Screenshots or exported flows
│   └── alert_flow_screenshot.png
├── requirements.txt          # Python dependencies
└── README.md                 # Project walkthrough
```

---

## 🎯 Objective

- Automate ticket priority classification (High, Medium, Low)
- Track and visualize misclassifications in Power BI
- Schedule Power BI dashboard using Power Automate

---

## 🔧 Tools Used

 ------------------------------------------------------------------------
| Tool              | Purpose                                            |
|-------------------|----------------------------------------------------|
| Python + Sklearn  | Text classification (TF-IDF + Logistic Regression) |
| DBeaver           | Data storage and SQL queries                       |
| Power BI          | Visualization and analysis                         |
| Power Automate    | Automated alerts and monitoring                    |
 ------------------------------------------------------------------------
---

## 🧪 Workflow Overview

1. **Load & Clean Data**  
   - Source: Customer support tickets
   - Clean and normalize ticket descriptions

2. **Train a Classifier**  
   - Model: Logistic Regression with TF-IDF features
   - SMOTE for handling class imbalance

3. **Store Predictions**  
   - Export model results to SQLite (`predicted_support_tickets` table)

4. **Visualize in Power BI**  
   - Confusion matrix, KPIs, error analysis

5. **Refresh dataset using Power Automate**  
   - Refresh the dashboard, export to PDF and send an Email on a daily basis

---

## 📊 Power BI Highlights

- **Stacked bar chart**: Actual vs Predicted Priority
- **Matrix**: Confusion Matrix
- **DAX Measures**:
  - Precision / Recall / F1 Score per class
  - Model Accuracy

---

## 🔔 Power Automate Integration

- Scheduled report delivery
- Sample representation of the Power Flow:
![Power Automate Flow](powerautomate\customer-tickets-pbi-schedule.png)
---

## 🚀 How to Run This Project

### 1. Setup Environment

```bash
pip install -r requirements.txt
```

### 2. Train the Model

Open `02_priority_classifier.ipynb` → run all cells to generate predictions

### 3. Upload to SQLite

Run `03_sql_upload.ipynb` to save predictions into `customer_tickets.db`

### 4. Open Power BI

Load the `.pbix` file from `/powerbi` or connect live to the DB

### 5. Setup Alerts (Optional)

Export refreshed dashboard to PDF and send a mail on daily basis(sechedule).

---

## 📌 Sample Output
 -------------------------
| Metric         | Score  |
|----------------|--------|
| Accuracy       |  73%   |
| High Precision |  26%   |
| Low F1 Score   |  20%   |
| Medium Recall  |  55%   |
 -------------------------

> Note: Results will vary based on class balance and model tuning.

---

## 💡 Future Enhancements

- Deploy model as a web API using Flask/ FastAPI/ Streamlit
- Incorporate sentiment scores and keyword features
- Schedule weekly retraining
- Fine-tune hyperparameters and try XGBoost

---

## 👩‍💻 Author

**Sneha Balan**  
Data Analyst | BI Developer | AI Enthusiast  
[LinkedIn](https://www.linkedin.com/in/your-profile)

---

## 📝 License

This project is for educational and demonstrative purposes.
