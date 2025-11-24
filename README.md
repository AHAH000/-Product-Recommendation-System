# 📦 Product Recommendation System

**Content-Based Similarity Model | ETL Pipeline | SQL Data Warehouse | Power BI Dashboard**

This project showcases a complete **end-to-end data engineering + data analytics pipeline**, built to generate product recommendations using a **content-based similarity model** and visualized through an interactive **Power BI dashboard**.

The project demonstrates skills across:

✔ Data Engineering
✔ ETL Pipelines
✔ SQL Data Warehousing (Star Schema)
✔ Python Automation
✔ Machine Learning (Cosine Similarity)
✔ Data Cleaning & Transformation
✔ Power BI Analytics & Visualization

---

# 🚀 Project Overview

This system recommends products based on **product attributes**, such as:

* Category
* Price
* Final Price
* Discount
* Payment Behavior

Using these attributes, a **cosine similarity model** calculates how similar each product is to every other product.
Top recommendations are then loaded into a **SQL Server Data Warehouse** and finally visualized in **Power BI**.

---

# 🧱 Project Architecture

```
            +------------------+
            |   Raw Dataset    |
            | (CSV File Input) |
            +------------------+
                     |
                     v
        +--------------------------+
        |   Python ETL Pipeline    |
        | - Cleaning               |
        | - Transformations        |
        | - Feature Engineering    |
        +--------------------------+
                     |
                     v
        +------------------------------+
        | SQL Server Data Warehouse    |
        | Dim Date / Dim Product /     |
        | Dim Customer / Fact Sales    |
        +------------------------------+
                     |
                     v
        +---------------------------+
        |  Recommendation Engine    |
        | - Cosine Similarity       |
        | - Top Recommended Items   |
        +---------------------------+
                     |
                     v
        +---------------------------+
        |  Power BI Dashboard       |
        | - KPIs                    |
        | - Price Analysis          |
        | - Category Distribution   |
        | - Recommendation Table    |
        +---------------------------+
```

---

# 📂 Folder Structure

```
product_recommendation_system/
│
├── data/
│   ├── raw/
│   │   └── ecommerce_dataset_updated.csv
│   ├── processed/
│   │   └── cleaned_transactions.csv
│   └── output/
│       └── content_based_recommendations.csv
│
├── scripts/
│   ├── transform.py     # Cleaning & preprocessing
│   ├── load.py          # Load into SQL DW
│   └── recommend.py     # Similarity model
│
├── warehouse/
│   └── schema.sql       # Star schema (DW)
│
└── dashboard/
    └── powerbi.pbix     # Power BI report
```

---

# 🧹 Step 1 — Data Cleaning & Transformation (transform.py)

Main transformations:

* Standardized column names
* Fixed date formats
* Converted prices/discounts to numeric
* Removed duplicates
* Ensured consistent product & customer IDs
* Exported clean dataset → `cleaned_transactions.csv`

---

# 🧮 Step 2 — Data Warehouse (SQL Server)

A **Star Schema** was designed:

### ⭐ Dimension Tables

* **Dim_Customers**
* **Dim_Products**
* **Dim_Date**

### ⭐ Fact Table

* **Fact_Transactions**
  Contains:
  `Transaction_ID`, `Price_Rs`, `Discount_%`, `Final_Price`, `Payment_Method`, `Date_ID`, etc.

Tables loaded using `load.py`.

---

# 🤖 Step 3 — Recommendation Engine (recommend.py)

A **content-based filtering** model was used:

### Steps:

1. Encode product features (category, price, final price).
2. Generate similarity matrix using **cosine similarity**.
3. For each product, find top N similar items.
4. Export results → `content_based_recommendations.csv`.

This dataset powers the dashboard.

---

# 📊 Step 4 — Power BI Dashboard

A full interactive dashboard includes:

### ⭐ Key Metrics

* Max / Min recommended price
* Price range of recommendations
* Average similarity score
* # of recommended products
* Price & category of selected base product

### ⭐ Visuals

* Donut chart (categories of recommendations)
* Scatter plot (price vs similarity score)
* Recommendations table
* KPI cards for quick insights
* Product slicer (base product selection)

The dashboard helps users understand:

✔ What products are most similar
✔ Price differences
✔ Categories recommended
✔ Strength of similarity scores

---

# 🎯 Skills Demonstrated

### **Data Engineering**

* ETL pipeline using Python
* Data cleaning & preprocessing
* Creating SQL ETL loaders
* Designing a star schema (Dim/Fact modeling)

### **Data Analytics**

* Business KPIs
* Price insights & distribution
* Category analysis
* Power BI dashboard development

### **Machine Learning**

* Vectorization of product features
* Cosine similarity matrix
* Rank-based recommendation system

---

# 🛠 Technologies Used

| Technology              | Purpose                          |
| ----------------------- | -------------------------------- |
| **Python**              | ETL, modeling                    |
| **Pandas, NumPy**       | Data transformation              |
| **scikit-learn**        | Cosine similarity                |
| **SQL Server (SSMS)**   | Data warehouse                   |
| **SQLAlchemy + pyodbc** | Database loading                 |
| **Power BI**            | Dashboard & analytics            |
| **mlxtend**             | (Optional) for other model types |

---

# 📌 How to Run the Project

### 1️⃣ Install dependencies

```sh
pip install -r requirements.txt
```

### 2️⃣ Run data cleaning

```sh
python scripts/transform.py
```

### 3️⃣ Load into SQL DW

```sh
python scripts/load.py
```

### 4️⃣ Generate recommendations

```sh
python scripts/recommend.py
```

### 5️⃣ Open Power BI file

Open `dashboard/powerbi.pbix`.

---

# 📷 Screenshots

*Add dashboard screenshots here once ready.*

---

# 📚 Future Improvements

* Add collaborative filtering model
* Add hybrid ensemble recommendation engine
* Deploy as an API using FastAPI
* Build a small Flask frontend to interact with the model
* Add real-time recommendations via SQL triggers

---

# 💬 Contact

If you'd like help improving the project or adding deployment, feel free to reach out.

---

If you want, I can also generate:

✅ A shorter README
✅ A more technical README
✅ A CV-optimized project summary
✅ A GitHub project description

Just tell me!
