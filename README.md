### **Vendor Performance Analysis Project**

-----

### **Project Overview**

This project is a complete end-to-end data analytics solution focused on evaluating and optimizing vendor performance. The pipeline handles large, raw transactional data, transforms it into a clean and unified dataset, and provides actionable business insights through a series of notebooks and a final interactive dashboard.

The key objective is to provide a 360-degree view of vendor performance, covering financial metrics, logistical efficiency, and inventory management.

### **Final Dashboard** 📊

The final outcome of this project is a dynamic dashboard built to provide key business insights at a glance. It summarizes complex data into intuitive visualizations, enabling stakeholders to make data-driven decisions.
<img width="885" height="495" alt="Screenshot (899)" src="https://github.com/user-attachments/assets/925493ec-199e-43b9-849b-eb9ec702202e" />


-----

### **Problem Statement**

In a fast-paced retail environment, understanding vendor performance is critical for maximizing profitability and optimizing the supply chain. Raw transactional data is often fragmented, incomplete, and too large to analyze directly. This project addresses these challenges by building a robust data pipeline that:

  * Efficiently ingests and processes large-scale data.
  * Cleans and consolidates data from multiple sources.
  * Calculates key performance indicators (KPIs) to measure vendor health.
  * Delivers a dynamic dashboard for data-driven decision-making.

-----

### **Project Structure**

The project is organized into three main phases, each represented by a Jupyter Notebook:

1.  **`Data_Ingestion_and_Setup.ipynb`**:

      * **Purpose**: This notebook initiates the data pipeline. It uses a **chunked ingestion** strategy to load large CSV files into a SQLite database (`inventory.db`) without exhausting memory resources.
      * **Key Tasks**:
          * Establish a database connection using `SQLAlchemy`.
          * Automate the loading of six raw CSV files (`sales`, `purchases`, `purchase_prices`, `vendor_invoice`, `begin_inventory`, `end_inventory`) into separate database tables.
          * Implement a logging system to track the ingestion process and handle potential errors.

2.  **`SQL_and_Pandas_Fusion_Analysis.ipynb`**:

      * **Purpose**: This is the core data transformation notebook. It leverages the power of SQL to perform complex aggregations and joins on the raw data. The goal is to create a single, pre-aggregated summary table for efficient analysis.
      * **Key Tasks**:
          * Connect to the `inventory.db` SQLite database.
          * Use advanced SQL queries with **Common Table Expressions (CTEs)** to aggregate purchase, sales, and freight data.
          * Create a consolidated `vendor_sales_summary` table that includes key metrics like `GrossProfit`, `ProfitMargin`, `StockTurnover`, and `SalesToPurchaseRatio`.
          * Clean the final dataset by handling missing values and correcting data types.

3.  **`Vendor_Analytics.ipynb`**:

      * **Purpose**: This notebook performs the final analysis and prepares the data for visualization. It connects to the `vendor_sales_summary` table to derive key business insights.
      * **Key Tasks**:
          * Calculate and analyze high-level performance metrics for the entire business.
          * Identify and rank **top-performing and bottom-performing vendors** based on various KPIs (e.g., Gross Profit, Sales, Purchase Dollars).
          * Create a range of professional visualizations, including bar charts and a correlation heatmap, to visually represent the findings.
          * Provide actionable business recommendations based on the data analysis, such as identifying opportunities for negotiation and inventory optimization.

-----

### **Technology Stack**

  * **Languages**: Python
  * **Libraries**:
      * `pandas`: For data manipulation and analysis.
      * `sqlalchemy`: For database connectivity and management.
      * `sqlite3`: To create and manage the local database.
      * `matplotlib` & `seaborn`: For data visualization.
  * **Database**: SQLite
  * **Dashboarding**: Power BI

-----

### **Key Insights & Recommendations**

  * **Profitability**: Identified the top 5 vendors contributing most to gross and net profit, highlighting opportunities for strategic partnerships.
  * **Inventory Efficiency**: Analyzed product turnover rates to pinpoint fast-moving items and optimize future purchasing decisions.
  * **Logistics**: Calculated the impact of freight costs per vendor, providing data-backed insights for future contract negotiations.

-----

### **How to Run the Project**

This guide will walk you through setting up and running the project locally.

#### **Step 1: Get the Project Files**

1.  **Clone the Repository**
    ```bash
    git clone https://github.com/YourUsername/Vendor-Performance-Analysis.git
    cd Vendor-Performance-Analysis
    ```

#### **Step 2: Prepare the Environment**

1.  **Install Required Libraries**
    ```bash
    pip install pandas sqlalchemy matplotlib seaborn
    ```
2.  **Unzip the Data**
      * Locate the `data.rar` (or `data.zip`) file in the repository.
      * Decompress the file. It should create a `data/` folder containing all the raw CSV files.
      * Place the `data/` folder at the root of the project directory.

#### **Step 3: Execute the Data Pipeline**

Run the notebooks in the following order to build the data pipeline:

1.  Open and run `Data_Ingestion_and_Setup.ipynb`. This notebook will ingest the raw data and create the `inventory.db` file.
2.  Next, open and run `SQL_and_Pandas_Fusion_Analysis`. This will execute the transformation logic and create the final `vendor_sales_summary` table in your database.
3.  Finally, open and run `Vendor_Analytics.ipynb`. This notebook contains the analysis and visualization code.

#### **Step 4: Connect to the Dashboard**

1.  Open your BI tool
2.  Connect to the `inventory.db` SQLite database file.
3.  Load the **`vendor_sales_summary`** table.
4.  You can now start building your dashboard using the pre-calculated metrics and dimensions from this table.
