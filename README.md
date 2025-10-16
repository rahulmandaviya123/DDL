# End-to-End Data Pipeline using Databricks Delta Live Tables

## 🚀 Project Overview
This project demonstrates how to design and implement a **real-world data engineering pipeline** using **Databricks Delta Live Tables (DLT)** on Azure.  
It follows the **Medallion Architecture (Bronze → Silver → Gold)** to enable **incremental**, **scalable**, and **reliable data processing** for an **e-commerce sales analytics** use case.

The goal of this project is to transform raw transactional data into **clean, business-ready insights** through automated data lineage, SCD management, and DLT pipeline orchestration.

---

## 🧩 Architecture
```
                ┌────────────────────────┐
                │   Raw Data Sources      │
                │ (Products, Customers,   │
                │   and Sales Data)       │
                └──────────┬──────────────┘
                           │
                      Bronze Layer
                  (Data Ingestion & Cleaning)
                           │
                      Silver Layer
          (Data Transformation & Enrichment)
                           │
                      Gold Layer
        (Business Aggregations & Analytics Models)
                           │
                   Visualization Tools
              (Power BI, Tableau, etc.)
```

---

## ⚙️ Technologies & Tools Used
| Category | Tools / Technologies |
|-----------|----------------------|
| Platform | Azure Databricks |
| Framework | Delta Live Tables (DLT) |
| Language | Python, PySpark |
| Storage | Azure Data Lake Gen2 |
| Processing | Spark Structured Streaming |
| Data Modeling | Medallion Architecture (Bronze, Silver, Gold) |
| Change Tracking | SCD Type 1 & Type 2 |
| Version Control | GitHub |
| Visualization | Power BI / Databricks SQL |

---

## 📂 Project Structure
```
DLT_Root/
├── explorations/               # Exploratory analysis scripts
│   └── sample_exploration.py
├── utilities/                  # Utility and helper functions
│   └── utils.py
├── transformations_SorceCode/
│   ├── bronze/                 # Ingestion layer
│   │   ├── ingestion_products.py
│   │   ├── ingestion_customers.py
│   │   └── ingestion_sales.py
│   ├── silver/                 # Transformation layer
│   │   ├── transform_products.py
│   │   ├── transform_customers.py
│   │   └── transform_sales.py
│   ├── gold/                   # Business & analytics layer
│       ├── dim_products.py
│       ├── dim_customers.py
│       ├── fact_sales.py
│       └── business_sales.py
│                    
│        
│     
└── README.md
```

---

## 🔁 Pipeline Flow
1. **Bronze Layer (Raw Data Ingestion)**  
   - Ingests raw data from multiple sources (CSV/Parquet/API).  
   - Performs schema validation and data cleaning.  

2. **Silver Layer (Data Transformation)**  
   - Applies business logic, joins datasets, and ensures referential integrity.  
   - Implements **incremental and streaming transformations**.  

3. **Gold Layer (Business & Analytics)**  
   - Creates **fact and dimension tables** for sales analysis.  
   - Handles **SCD Type 1 and Type 2** logic for product and customer changes.  
   - Prepares final curated tables for reporting dashboards.  

---

## 🧱 Key Features
- ✅ Delta Live Tables for **automated pipeline management**
- ✅ Supports **incremental batch and streaming loads**
- ✅ Implements **SCD Type 1 and 2** for change tracking
- ✅ Follows **Medallion Architecture** best practices
- ✅ Easy integration with **Power BI / Databricks SQL**
- ✅ Modular, reusable Python code structure

---

## 🧪 How to Run the Project in Databricks
1. Clone this repository into your Databricks workspace:
   ```bash
   git clone https://github.com/<your-username>/DLT_Root.git
   ```
2. Import the project folder into Databricks Repos.  
3. Open each notebook/script under `transformations_SorceCode/`.  
4. Create a new **Delta Live Tables Pipeline** in Databricks:
   - Pipeline Source: this repo path  
   - Target: your database name (e.g., `databricks_catalog.gold`)  
   - Storage Location: Azure Data Lake path  
5. Run the pipeline and monitor:
   - Lineage view  
   - Job metrics  
   - Error handling and recovery  

---

## 🌐 Real-World Use Case
This project simulates a real-world **e-commerce data pipeline** that:
- Tracks daily product sales across multiple regions.  
- Updates customer and product master data with history tracking.  
- Produces business insights such as revenue trends, top products, and customer lifetime value.  

---

## 📊 Lineage and Monitoring
DLT provides an automatic **data lineage graph**, enabling you to visualize dependencies across tables:
```
bronze_sales → silver_sales → gold_fact_sales
bronze_customers → silver_customers → gold_dim_customers
bronze_products → silver_products → gold_dim_products
```

---

## 🧰 Future Enhancements
- Add CI/CD pipeline for Databricks Repos  
- Integrate Data Quality checks using **Expectations**  
- Extend to multi-source ingestion (API, Kafka)  
- Add Databricks Workflows for orchestration  

---

## 👨‍💻 Author
**Rahul Mandaviya**  
📍 Data Engineer | Azure | Databricks | Power BI  
🔗 [LinkedIn Profile](https://www.linkedin.com/in/rahul-mandaviya/)
