# World Layoffs Data Cleaning (SQL Project)

This project demonstrates a **SQL-based data cleaning workflow** using a layoffs dataset.  
The goal is to show step-by-step cleaning techniques commonly used in real-world analytics projects.

---

## 📊 Project Overview
The dataset (`world_layoffs.layoffs`) contains company layoff records, including details such as:
- Company, industry, location
- Number of employees laid off
- Funding, stage, and country information
- Date of layoffs

The raw data includes duplicates, inconsistent formatting, null values, and other issues that must be addressed before meaningful analysis.

---

## 🛠️ Steps in Data Cleaning
The cleaning process follows a structured approach:

1. **Create a Staging Table**  
   - A copy of the raw table is created for cleaning (`layoffs_staging`, `layoffs_staging2`)  
   - Keeps the raw data intact for reference

2. **Remove Duplicates**  
   - Used `ROW_NUMBER()` with `PARTITION BY` to identify duplicate rows  
   - Deleted duplicates while keeping one clean version of each record

3. **Standardize Data**  
   - Converted blank strings to `NULL` for easier handling  
   - Standardized inconsistent values (e.g., `"CryptoCurrency"` → `"Crypto"`, `"United States."` → `"United States"`)  
   - Converted `date` column from `TEXT` to proper `DATE`

4. **Handle Null Values**  
   - Retained nulls where they made sense (`total_laid_off`, `percentage_laid_off`)  
   - Removed rows where **both `total_laid_off` and `percentage_laid_off`** were missing

5. **Drop Unnecessary Columns**  
   - Removed helper column (`row_num`) after cleaning

---

## 📂 Files
- `sql/layoffs_data_cleaning.sql` → Full SQL script with explanations
- `docs/before_after_snapshots.md` → (Optional) Example queries showing the dataset before & after cleaning

---

## 🚀 Skills Demonstrated
- SQL Window Functions (`ROW_NUMBER()`)
- Data standardization and formatting
- Null handling strategies
- Schema modifications (`ALTER TABLE`, `DROP COLUMN`)
- Documentation of data cleaning workflow

---

## 🔮 Next Steps
This dataset can now be used for:
- Exploratory Data Analysis (EDA)  
- Trend analysis of layoffs across industries and countries  
- Predictive modeling

---

## 📜 License
This project is open-source under the [MIT License](LICENSE).

---
