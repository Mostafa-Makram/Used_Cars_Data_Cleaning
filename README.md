# Used Cars Data Cleaning & Preprocessing

A data cleaning and preprocessing project for a used-cars dataset using Python, Pandas, and Scikit-learn. The workflow explores 3,000 vehicle listings, handles missing and duplicate records, standardizes categorical values, engineers features, encodes categorical columns, and prepares the data for a classification task.

## Dataset

The dataset contains **3,000 rows and 18 columns** describing used-car listings.

Main feature groups include:
- **Vehicle details:** brand, model, year, mileage, transmission, fuel type, engine size, body type, and color.
- **Listing details:** city, seller type, accident history, previous owners, condition rating, photo count, and price in EGP.
- **Target:** `sold_within_30_days` — whether the car was sold within 30 days.

## Work Performed

- Inspected the dataset structure, column types, summary statistics, and missing-value counts.
- Filled missing values using median, mode, or zero according to the column and its meaning.
- Removed duplicate records.
- Standardized text values by trimming whitespace, converting text to lowercase, and normalizing repeated spaces.
- Unified inconsistent category labels, including transmission and accident-history values.
- Checked numerical columns for suspicious or invalid values, such as non-positive prices, negative mileage, and invalid years.
- Explored distributions and relationships using Matplotlib and Seaborn.
- Created a `car_age` feature and removed the original `year` column.
- Combined `brand` and `model` into a `brand_model` feature.
- Grouped less frequent cities into an `Others` category.
- Encoded categorical features using Label Encoding, Ordinal Encoding, and One-Hot Encoding.
- Separated features and target, then created training and testing sets.

## Tools & Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Repository Contents

```text
.
├── Untitled-1.ipynb
├── used_cars_dataset.csv
└── README.md
```

## How to Run

1. Clone or download this repository.
2. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```

3. Open the notebook:

   ```bash
   jupyter notebook
   ```

4. Run the notebook cells in order. Make sure `used_cars_dataset.csv` is in the same directory as the notebook.

## Notes & Next Steps

- The notebook currently identifies suspicious numerical records; review those rows and decide whether to correct or remove them before modeling.
- For a leakage-safe modeling workflow, split the data first and fit imputers, encoders, and scalers on the training data only. In particular, fit `StandardScaler` on `X_train` and use the fitted scaler to transform `X_test`.
- The `car_age` calculation uses a fixed reference year (2026); update it when reusing the notebook in a later year.

## Project Goal

Prepare a consistent, analysis-ready dataset for exploring and modeling the factors associated with whether a used car sells within 30 days.
