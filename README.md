### **Transaction Data Cleaning and Analysis in Power BI**

This project focuses on data cleaning, transformation, and analysis using Power BI. The primary goal is to process and analyze transaction data across two years, integrating additional dimensional data for comprehensive insights. The following datasets are used:

- **fact_transactions_2022**
- **fact_transactions_2023**
- **dim_merchants**
- **pivoted_dim_category**
- **dim_date**

#### **Tasks Overview:**

**Task 1: Data Cleaning in `dim_merchants` Table**
- **Objective:** Standardize and clean the merchant names for consistent data.
  - **Steps:**
    - Split the `Merchant` column into two parts based on a common delimiter. For example, “Apollo Pharmacy - (Mid-sized)” is split into "Apollo Pharmacy" and "(Mid-sized)".
    - Remove leading and trailing spaces from the new `Industry Segment` column using the **Trim** function.
    - Eliminate unnecessary characters like parentheses “(” and “)” from the `Industry Segment` column by extracting values using **Text Between Delimiters**.
    - Remove duplicate merchants that have different IDs to ensure uniqueness.

**Task 2: Extracting Date Information from `dim_date` Table**
- **Objective:** Decompose the date field into individual components for easier analysis.
  - **Steps:**
    - Break down the date field into `Year`, `Month Name`, and `Day Name`.
    - Create separate columns for each component.

**Task 3: Unpivoting the `pivoted_dim_category` Table**
- **Objective:** Transform the category data into a format suitable for merging with fact tables.
  - **Steps:**
    - Perform row transformations and apply the **Unpivot** operation to bring the data into the desired format.
    - Rename the transformed table to `dim_category`.

**Task 4: Filtering Unwanted Data**
- **Objective:** Focus on significant transactions by filtering out low-value transactions.
  - **Steps:**
    - Filter out transactions with a `Debit_Amount` below 100 from both `fact_transactions_2022` and `fact_transactions_2023` tables.

**Task 5: Appending Tables**
- **Objective:** Combine transaction data from two years into a single dataset.
  - **Steps:**
    - Append the `fact_transactions_2023` data to the `fact_transactions_2022` table.
    - Store the combined data in a new table named `fact_transactions`.

**Task 6: Merging Tables**
- **Objective:** Integrate transaction data with dimensional data for enriched analysis.
  - **Steps:**
    - Merge the `fact_transactions` table with `dim_category` and `dim_merchants` to retrieve corresponding merchant and category names.

**Task 7: Adding a Conditional Column**
- **Objective:** Classify transactions into categories based on the amount.
  - **Steps:**
    - Create a new column named `Transaction Category`:
      - Label transactions with amounts below 1000 as `Low`.
      - Label transactions with amounts above 1000 as `High`.

**Task 8: Sorting and Grouping**
- **Objective:** Analyze and rank merchants based on their total transaction amounts.
  - **Steps:**
    - Duplicate the `fact_transactions` table for analysis purposes.
    - Group the data by `Merchant` and calculate the total transaction amount.
    - Sort the merchants based on the total transaction amounts.

---

This project demonstrates the complete process of cleaning, transforming, and analyzing transaction data using 
Power BI, making it easier to gain insights from the data. The steps outlined ensure that the data is in a consistent and 
usable format, allowing for effective reporting and analysis.
