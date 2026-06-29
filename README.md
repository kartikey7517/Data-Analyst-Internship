# Data-Analyst-Internship
To ensure data integrity, **I did not modify the original Excel file** (it's an industry best practice to keep the raw data untouched).

Instead, the Python script ran and generated a **new cleaned file** ('cleaned_superstore_sales.csv'). Here is a short summary of the changes made from the raw data to the new CSV file:

1. **Removed Useless Columns:** Dropped the `ind1` and `ind2` columns because they were 100% empty (null).
2. **Standardized Column Names:** Converted all column names to lowercase and replaced spaces with underscores (e.g., `Order Date` -> `order_date`). Also, fixed a malformed column name `Row ID+O6G3A1:R6` by renaming it to simply `row_id`.
3. **Fixed Missing Values:** Filled the missing (NaN) values in the `Returns` column with `0` (since a blank in this context means the order was not returned).
4. **Added 4 New Columns (Feature Engineering):**
   * `processing_days`: The difference between Ship Date and Order Date (useful for tracking shipping speed).
   * `order_year` & `order_month`: Extracted from the date for easier filtering in dashboards.
   * `is_outlier_sales`: Added a True/False flag using the IQR method to easily identify massive, unusual orders.

Because all of these changes were saved into the new `cleaned_superstore_sales.csv` file, your original Excel data remains completely safe and untouched!
