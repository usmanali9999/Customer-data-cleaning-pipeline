# Customer Call Data Cleaning Pipeline

## 📌 Project Overview
This repository contains a professional Python-based data cleansing pipeline that transforms a chaotic, user-inputted customer directory into a structured, database-ready asset. In real-world enterprise databases, customer lists frequently suffer from duplicate entries, inconsistent phone formats, manual input errors, and corrupted structural schemas. This project builds a reliable script to clean, validate, and standardize contact information for downstream corporate operations.

* **Target Applications:** CRM Synchronization, Direct Marketing Automation, Data Auditing.
* **Core Technology Stack:** Python 3, Pandas, NumPy, Jupyter Notebook.

---

## 📊 The "Before vs. After" Data Transformation

The pipeline successfully resolved major data integrity issues across the source dataset:

### 1. Structural Schema Standardization
* **Before:** Address data was collapsed inside a single compound text field (`Address`), mixed with irrelevant metadata attributes (`Not_Useful_Column`).
* **After:** Irrelevant attributes were discarded. The compound geographic field was parsed into three clean, granular database attributes: `street`, `state`, and `zipcode`.

### 2. Contact Field Normalization (`Phone_Number`)
* **Before:** Inconsistent phone strings including mixed delimiters (`123/643/9775`), lack of structural spacing (`7066950392`), and corrupted textual placeholders (`N/a`).
* **After:** Unified into a standardized 10-digit format with strict hyphen separation (`###-###-####`). Incomplete or corrupted fields are systematically converted to official missing values (`NaN`).

### 3. Categorical Value Consolidation (`Paying Customer` & `Do_Not_Contact`)
* **Before:** Multi-variant, mixed-case user responses containing text variants like `Yes`, `Y`, `y`, `No`, `N`, `n`, and `N/a`.
* **After:** Standardized into clean, uniform, production-ready strings (`Yes` or `No`), completely eliminating classification duplicates.

### 4. Deduplication & Syntax Scrubbing
* **Before:** The dataset contained identical duplicate records (such as duplicate entries for `Anakin Skywalker`) and messy text prefixes/suffixes (like `/White` and `...Potter`).
* **After:** Dropped all trailing duplicate profiles to preserve database truth and completely scrubbed syntax noise from name attributes.

---

## 🛠️ Project File Architecture

The repository is structured following industry-standard data engineering practices:
* `01_Customer Call List.xlsx` - Raw, uncleaned customer data source file.
* `02_Customer_Call_List_Cleaned.csv` - Final, production-ready, standardized output data file.
* `03_Customer_Call_Cleaning.ipynb` - Documented Python cleaning pipeline with inline code commentary.
* `requirements.txt` - Complete environment configuration file containing package dependencies.

---

## 🚀 How To Run the Project

### 1. Environment Setup
Clone this repository to your local directory and install the necessary package dependencies using the provided requirements configuration file:
```bash
pip install -r requirements.txt
## Execution Steps

1. Clone this repository to your machine:
   ```bash
   git clone https://github.com
   cd customer-clean-project
   ```

2. Start the Jupyter workspace environment:
   ```bash
   jupyter notebook
   ```

3. Open and run all cell groups inside `03_Customer_Call_Cleaning.ipynb` to regenerate the live data.

