# Task 15: NumPy Statistical Analysis

## Description
Analyze a numerical dataset using NumPy statistical functions and identify important patterns in the data.

## Objective
Practice applying statistical functions to numerical data.

## Tools Used
* Python
* NumPy
* Jupyter Notebook

---

## 1. Code Implementation

```python
import numpy as np

# Setting a seed for reproducibility
np.random.seed(42)

# Generate 30 days of sales data, mostly between $100 and $500, with an outlier
sales_data = np.random.normal(loc=300, scale=100, size=29)
sales_data = np.append(sales_data, [1200]) # Adding one unusually high sales day
sales_data = np.round(sales_data, 2) # Round to 2 decimal places for currency

print("Simulated Sales Dataset (30 days):\n", sales_data)
print("\n--- Statistical Calculations ---")

# Statistical calculations using NumPy
mean_sales = np.mean(sales_data)
median_sales = np.median(sales_data)
std_dev_sales = np.std(sales_data)
min_sales = np.min(sales_data)
max_sales = np.max(sales_data)

print(f"Mean Sales: ${mean_sales:.2f}")
print(f"Median Sales: ${median_sales:.2f}")
print(f"Standard Deviation: ${std_dev_sales:.2f}")
print(f"Minimum Sales: ${min_sales:.2f}")
print(f"Maximum Sales: ${max_sales:.2f}")
```

## 2. Results

**Simulated Sales Dataset (30 days):**
```text
[ 349.67  286.17  364.77  452.3   276.58  276.59  457.92  376.74  253.05
  354.26  253.66  253.43  324.2   108.67  127.51  243.77  198.72  331.42
  209.2   158.77  446.56  277.42  306.75  157.53  245.56  311.09  184.9
  337.57  239.94 1200.  ]
```

**Statistical Output:**
* **Mean Sales:** $312.16
* **Median Sales:** $277.00
* **Standard Deviation:** $187.10
* **Minimum Sales:** $108.67
* **Maximum Sales:** $1200.00

---

## 3. Observations

1. **Comparison of Mean and Median:** The mean sales value ($312.16) is noticeably higher than the median sales value ($277.00). This indicates a right-skewed distribution, meaning that a few extremely high values are pulling the average up artificially.
2. **Unusually High Value (Outlier):** The maximum sales value is $1200.00, which is significantly higher than the rest of the dataset. This represents a major outlier, perhaps due to a special promotion, a bulk order, or a data entry error. 
3. **Data Spread:** The standard deviation is quite high ($187.10) relative to the median and mean. This suggests that daily sales are quite variable and not very consistent from day to day, heavily influenced by that large outlier.

---

## 4. Interview Questions

**1. What is the difference between mean and median?**
*   **Mean (Average):** The sum of all values in a dataset divided by the total number of values. It incorporates every single data point into its calculation.
*   **Median:** The middle value when a dataset is ordered from least to greatest. If there is an even number of values, it's the average of the two middle numbers. It only considers positional rank, not the specific values of the extreme ends.

**2. When can median be more useful than mean?**
The median is more useful than the mean when a dataset has outliers (extreme high or low values) or is strongly skewed. Because the mean incorporates every value, an extreme outlier will significantly pull the average in its direction, giving a misleading representation of the "typical" value. The median is resistant to outliers because it only looks at the middle position, providing a better measure of central tendency in such cases (like average income or housing prices).

**3. What does standard deviation tell us?**
Standard deviation measures the amount of variation or dispersion in a set of values.
*   A **low standard deviation** indicates that the values tend to be close to the mean (the data is tightly clustered and consistent).
*   A **high standard deviation** indicates that the values are spread out over a wider range from the mean. It helps you understand how consistent or predictable your data is.
