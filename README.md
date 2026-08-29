# 🏗️ SQL Data Warehouse Project

## 📌 Project Overview

This project demonstrates the design and implementation of a **modern Data Warehouse using Microsoft SQL Server and T-SQL**.

The main objective is to take raw data from different source systems, clean and transform it through an ETL process, integrate the data into a structured warehouse, and prepare it for analytics and reporting.

The project follows a **Medallion Architecture** consisting of three layers:

* 🥉 **Bronze Layer** – Raw data
* 🥈 **Silver Layer** – Cleaned and transformed data
* 🥇 **Gold Layer** – Business-ready analytical data

The project demonstrates practical Data Engineering concepts including **ETL, data cleansing, data integration, data modeling, SQL development, and data quality testing**.

---

# 🎯 Project Objectives

The key objectives of this project are:

* Build a data warehouse using **SQL Server**
* Design a layered data warehouse architecture
* Load data from multiple source systems
* Perform ETL using T-SQL
* Clean and standardize raw data
* Integrate CRM and ERP datasets
* Build analytical data models
* Implement data quality checks
* Create business-ready datasets for analytics
* Maintain the project using Git and GitHub

---

# 🏛️ Data Warehouse Architecture

The project follows a three-layer architecture:

```text
                    SOURCE SYSTEMS
              ┌───────────────────────┐
              │                       │
              │        CRM            │
              │                       │
              │  Customers            │
              │  Products             │
              │  Sales                │
              │                       │
              └───────────┬───────────┘
                          │
                          │
              ┌───────────▼───────────┐
              │                       │
              │        ERP            │
              │                       │
              │ Customers             │
              │ Locations             │
              │ Product Categories    │
              │                       │
              └───────────┬───────────┘
                          │
                          ▼
                ┌───────────────────┐
                │   🥉 BRONZE       │
                │                   │
                │    Raw Data       │
                │                   │
                └─────────┬─────────┘
                          │
                          ▼
                ┌───────────────────┐
                │   🥈 SILVER       │
                │                   │
                │ Cleaned &         │
                │ Transformed Data  │
                │                   │
                └─────────┬─────────┘
                          │
                          ▼
                ┌───────────────────┐
                │    🥇 GOLD        │
                │                   │
                │ Business-Ready    │
                │ Analytical Data   │
                │                   │
                └─────────┬─────────┘
                          │
                          ▼
                ┌───────────────────┐
                │    ANALYTICS      │
                │                   │
                │ SQL / BI / Reports│
                │                   │
                └───────────────────┘
```

---

# 🔄 ETL Process

The ETL process transforms raw source data into analytical data through multiple stages.

```text
Extract
   ↓
Load Raw Data
   ↓
Bronze Layer
   ↓
Clean & Transform
   ↓
Silver Layer
   ↓
Integrate & Model
   ↓
Gold Layer
   ↓
Analytics & Reporting
```

## 1. Extract

Data is provided through CSV files representing different source systems.

The project contains data from:

### CRM

* Customer information
* Product information
* Sales information

### ERP

* Customer information
* Location information
* Product category information

---

# 🥉 Bronze Layer

The Bronze layer is the **raw data layer**.

The purpose of this layer is to store source data with minimal transformation.

### Responsibilities

* Load raw source data
* Preserve the original structure as much as possible
* Provide a staging area for downstream processing
* Maintain a clear separation between raw and transformed data

The Bronze layer contains data originating from both **CRM and ERP systems**.

```text
CRM / ERP
    ↓
Raw CSV Files
    ↓
Bronze Tables
```

---

# 🥈 Silver Layer

The Silver layer is responsible for **data cleansing and transformation**.

Data from the Bronze layer is processed and prepared for integration.

### Main activities

* Data cleansing
* Data type conversion
* Handling invalid values
* Standardizing attributes
* Removing unwanted duplicates
* Applying business transformation rules
* Preparing data for integration

```text
Bronze
   ↓
Data Cleaning
   ↓
Data Standardization
   ↓
Data Transformation
   ↓
Silver
```

---

# 🥇 Gold Layer

The Gold layer contains **business-ready data**.

This layer is designed for analytical workloads and reporting.

The transformed data from the Silver layer is integrated and organized into a structure that is easier for analysts and BI tools to consume.

### Main objectives

* Create business-friendly datasets
* Integrate related entities
* Apply business logic
* Create analytical data models
* Provide data suitable for reporting and analysis

```text
Silver
   ↓
Business Logic
   ↓
Data Integration
   ↓
Data Modeling
   ↓
Gold
```

---

# 📊 Data Modeling

The Gold layer uses a structured data model to organize business entities and their relationships.

The model is designed to make analytical queries easier and more efficient.

The project demonstrates concepts such as:

* Fact tables
* Dimension tables
* Primary keys
* Foreign keys
* Relationships
* Surrogate keys
* Business entities

The data model helps transform operational source data into a structure suitable for analytical workloads.

---

# 🔗 Data Integration

An important part of this project is integrating data from different source systems.

The project uses data from both:

```text
CRM System
    │
    ├── Customers
    ├── Products
    └── Sales
    │
    ▼
Data Warehouse
    ▲
    │
    ├── Customers
    ├── Locations
    └── Product Categories
    │
ERP System
```

The integration process combines related information from these sources and prepares it for analytical use.

---

# 🧪 Data Quality & Testing

Data quality is an important part of the warehouse development process.

The project includes SQL-based validation scripts to check the quality of transformed data.

The `tests` directory contains data quality checks for:

* Silver layer
* Gold layer

These checks help identify issues such as:

* Missing values
* Duplicate records
* Invalid relationships
* Incorrect data types
* Unexpected values
* Data consistency problems

```text
Source Data
    ↓
ETL Processing
    ↓
Data Quality Checks
    ↓
Validated Data
    ↓
Analytics
```

---

# 📂 Repository Structure

```text
Sql-data-warehouse-project/
│
├── 📁 Datasets/
│   │
│   ├── 📁 Source_crm/
│   │   ├── cust_info.csv
│   │   ├── prd_info.csv
│   │   └── sales_details.csv
│   │
│   └── 📁 Source_erp/
│       ├── CUST_AZ12.csv
│       ├── LOC_A101.csv
│       └── PX_CAT_G1V2.csv
│
├── 📁 Docs/
│   ├── ETL.png
│   ├── data_architecture.png
│   ├── data_flow.png
│   ├── data_integration.png
│   ├── data_layers.pdf
│   └── data_model.png
│
├── 📁 Scripts/
│   │
│   ├── 📁 bronze/
│   │
│   ├── 📁 Silver/
│   │
│   ├── 📁 Gold/
│   │
│   └── init_database.sql
│
├── 📁 tests/
│   ├── quality_checks_silver.sql
│   └── quality_checks_gold.sql
│
└── README.md
```

---

# 🛠️ Technologies Used

| Technology               | Purpose                                  |
| ------------------------ | ---------------------------------------- |
| **Microsoft SQL Server** | Data warehouse platform                  |
| **T-SQL**                | ETL, transformation and data modeling    |
| **CSV**                  | Source data                              |
| **Git**                  | Version control                          |
| **GitHub**               | Source code management and collaboration |

---

# 📁 Project Components

## `Datasets/`

Contains the source datasets used by the data warehouse.

The datasets are organized according to their source systems.

```text
Datasets/
│
├── Source_crm/
│
└── Source_erp/
```

---

## `Docs/`

Contains the project documentation and architecture diagrams.

Examples include:

* ETL architecture
* Data architecture
* Data flow
* Data integration
* Data layers
* Data model

---

## `Scripts/`

Contains the SQL scripts used to create and populate the data warehouse.

The scripts are organized according to the warehouse layers.

```text
Scripts/
│
├── bronze/
├── Silver/
└── Gold/
```

---

## `tests/`

Contains SQL scripts used to perform data quality validation.

```text
tests/
│
├── quality_checks_silver.sql
└── quality_checks_gold.sql
```

---

# 🚀 How to Run the Project

## Step 1 — Clone the Repository

```bash
git clone https://github.com/Rezex0/Sql-data-warehouse-project.git
```

## Step 2 — Open SQL Server

Open the project using **SQL Server Management Studio (SSMS)** or another compatible SQL client.

## Step 3 — Initialize the Database

Run:

```text
Scripts/init_database.sql
```

## Step 4 — Load the Bronze Layer

Execute the SQL scripts under:

```text
Scripts/bronze/
```

This loads the raw source data.

## Step 5 — Process the Silver Layer

Execute the Silver-layer scripts under:

```text
Scripts/Silver/
```

This cleans and transforms the Bronze data.

## Step 6 — Build the Gold Layer

Execute the scripts under:

```text
Scripts/Gold/
```

This creates the business-ready analytical layer.

## Step 7 — Run Data Quality Checks

Execute:

```text
tests/quality_checks_silver.sql
tests/quality_checks_gold.sql
```

to validate the processed data.

---

# 🔍 End-to-End Data Flow

The complete project workflow can be summarized as:

```text
                 SOURCE SYSTEMS
                       │
             ┌─────────┴─────────┐
             │                   │
            CRM                 ERP
             │                   │
             └─────────┬─────────┘
                       │
                       ▼
                🥉 BRONZE
                 Raw Data
                       │
                       ▼
                🥈 SILVER
           Clean & Transform
                       │
                       ▼
                 🥇 GOLD
           Business-Ready Data
                       │
                       ▼
                 ANALYTICS
```

---

# 💡 Key Data Engineering Concepts Demonstrated

This project demonstrates practical knowledge of:

### Data Engineering

* ETL
* Data ingestion
* Data transformation
* Data integration
* Data cleansing
* Data validation
* Data quality

### Data Warehousing

* Data warehouse architecture
* Medallion architecture
* Bronze/Silver/Gold layers
* Fact and dimension modeling
* Data relationships
* Analytical data structures

### SQL

* T-SQL
* DDL
* DML
* Stored procedures
* Joins
* CTEs
* Window functions
* Data transformation
* Data validation

### Development Practices

* Git
* GitHub
* Project documentation
* Organized SQL scripts
* Testing and validation

---

# 🔮 Future Improvements

Potential future improvements include:

* Implementing automated CI/CD for SQL scripts
* Adding automated data quality checks
* Adding orchestration for scheduled ETL execution
* Building an analytics dashboard
* Adding monitoring and logging
* Improving pipeline error handling
* Expanding analytical use cases

---

# 📚 Documentation

Detailed project documentation and architecture diagrams are available in the [`Docs`](Docs/) directory.

The documentation includes:

* ETL design
* Data architecture
* Data flow
* Data integration
* Data layers
* Data model

---

# 👤 Author

## Rupam Goswami

**Data & Analytics | SQL | Python | Power BI | Data Engineering**

GitHub: [@Rezex0](https://github.com/Rezex0)

---

# ⭐ Project

If you find this project useful, feel free to explore the repository and review the SQL implementation.

**Built to demonstrate practical SQL Data Warehousing and Data Engineering skills.**
