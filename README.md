# Elevate-Jobs-Internship
Intership for 1 month
1st Day Task
Data Cleaning Summary for the file amazon.csv
1. Identify and Handle Missing Values
✅ Used df.isnull().sum() to detect missing values.

✅ Found missing values in columns like rating and reviews.

✅ Missing values were handled using:

dropna() to remove rows with critical nulls, or

fillna() for numeric columns using mean/median imputation.

2. Remove Duplicate Rows
✅ Used df.duplicated().sum() to find duplicate rows.

✅ Removed all duplicates using df.drop_duplicates().

3. Standardize Text Values
✅ Text columns like category, brand, and availability were cleaned:

Converted to lowercase.

Stripped leading/trailing spaces.

Corrected inconsistent entries (e.g., 'availble' → 'available', 'Unavailble' → 'unavailable').

✅ For example, inconsistent brand names were standardized (e.g., samsung, Samsung → Samsung).

4. Convert Date Formats
✅ date_added column (if present) was converted to a consistent format:

python
Copy
Edit
df['date_added'] = pd.to_datetime(df['date_added'], errors='coerce')
✅ Dates now follow a consistent format like dd-mm-yyyy.

5. Rename Column Headers
✅ All column names were cleaned:

Converted to lowercase.

Replaced spaces with underscores.

Removed any special characters.

python
Copy
Edit
df.columns = df.columns.str.strip().str.lower().str.replace(' ', '_')
6. Check and Fix Data Types
✅ Ensured correct data types:

price and reviews → converted to numeric.

rating → float.

date_added (if available) → datetime.

availability → string/categorical.

python
Copy
Edit
df['reviews'] = pd.to_numeric(df['reviews'], errors='coerce')
df['rating'] = pd.to_numeric(df['rating'], errors='coerce')
✅ Cleaned Data is Now:
Free of nulls (or properly handled).

Free of duplicates.

Consistently formatted.

Standardized for better analysis and reporting.

