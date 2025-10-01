# World Layoffs Data Cleaning (SQL Project)

This project demonstrates a **SQL-based data cleaning workflow** on a global layoffs dataset.  
It highlights the process of preparing raw data for analysis: handling duplicates, fixing inconsistencies, managing null values, and cleaning schema issues.

---

## 📊 Dataset
- **File:** `data/layoffs_raw.csv`  
- Contains company layoff records, with columns such as:
  - Company, location, industry
  - Total laid off, percentage laid off
  - Date, stage, country, funding information  

---

## 🛠️ Data Cleaning Steps
The SQL script (`sql/layoffs_data_cleaning.sql`) covers:

1. **Staging the Data**  
   - Created staging tables (`layoffs_staging`, `layoffs_staging2`) to preserve raw data.

2. **Removing Duplicates**  
   - Used `ROW_NUMBER()` with `PARTITION BY` to identify duplicates.  
   - Deleted duplicate rows while preserving unique records.

3. **Standardizing Data**  
   - Converted blank strings → `NULL`  
   - Standardized industry names (e.g., `"CryptoCurrency"` → `"Crypto"`)  
   - Fixed inconsistent country names (e.g., `"United States."` → `"United States"`)  
   - Converted `date` from `TEXT` → `DATE`

4. **Handling Null Values**  
   - Retained nulls in useful columns for analysis  
   - Deleted rows where both `total_laid_off` and `percentage_laid_off` were missing

5. **Schema Cleanup**  
   - Dropped helper columns (`row_num`) after cleaning

---

## 📂 Project Structure
