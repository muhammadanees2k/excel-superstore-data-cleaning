# Dataset Cleaning for Superstore Analysis

## Dataset Name: `superstore_raw`
- **Total number of columns**: 21  

## Purpose:
To clean the store dataset and prepare it for further analysis.

---

## 🔍 Before Cleaning

![Before Cleaning Dataset](Images/before_cleaning.png)

---

## 🛠️ Cleaning Steps

### 1. Format the Header
- Format **Row #1** for visual clarity.
- Remove spaces from column headers to ensure consistency.



---

### 2. Fix Inconsistencies in the Order Date Column
- Some dates in the **Order Date** column are stored as text. To correct this:
  1. Select the **Order Date** column.
  2. Go to the **Data** tab.
  3. Choose **Text to Columns**, select the date format `MM-DD-YYYY`, and apply.

---

### 3. Fix Inconsistencies in the Ship Date Column
- Apply the same steps used for the **Order Date** column to correct inconsistencies in the **Ship Date** column.

---

### 4. Format Sales, Discount, and Profit Columns
- Ensure the **Sales**, **Discount**, and **Profit** columns:
  - Are formatted as **Currency**.
  - Are limited to **two decimal places** for consistency.

---

### 5. Convert Negative Values in the Profit Column
- Some values in the **Profit** column are enclosed in round brackets (e.g., `(500)`), indicating negative values in accounting format.
- To convert them to actual negative numbers, use the following formula in a new column:

    ```excel
    =IF(LEFT(U2,1)="(", -SUBSTITUTE(SUBSTITUTE(U2,"(",""),")",""), U2)
    ```

- After applying the formula:
  - Copy the new column.
  - Use **Paste Values** to remove the formula.
  - Delete the original **Profit** column.
  - Rename the new column back to **Profit**.

![Profit Column Cleaned](Images/after_cleaning_one.png)


![Profit Column Cleaned](Images/after_cleaning_two.png)

---

## ✅ Final Result:
The dataset is now clean, consistent, and ready for further analysis.

