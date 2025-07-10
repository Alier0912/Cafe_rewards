# Cafe Rewards Data Cleaning & Preparation

  -  This project demonstrates how to clean, transform, and prepare data for analysis using Python.
  -  The main workflow is contained in the `Cleaning&Preparation.ipynb` Jupyter notebook.

## Project Structure

- `Cleaning&Preparation.ipynb`: Main notebook for data cleaning and preparation.
- `customers.csv`, `events.csv`, `offers.csv`, `data_dictionary.csv`: Datasets used in the notebook.

## Getting Started

### 1. Uploading Files

Place the following files in the project directory:
- `customers.csv`
- `events.csv`
- `offers.csv`
- `data_dictionary.csv`

You can upload these files using the Jupyter Notebook interface or by copying them directly into the folder.

### 2. Connecting Files

The notebook uses `pandas` to load the datasets:

```python
import pandas as pd

customers = pd.read_csv('customers.csv')
events = pd.read_csv('events.csv')
offers = pd.read_csv('offers.csv')
```

### 3. Data Cleaning

- **Parsing JSON-like columns:**  
  The `value` column in `events.csv` is converted from a string to a Python dictionary using `ast.literal_eval`.
- **Extracting fields:**  
  Offer IDs, amounts, and rewards are extracted from the `value` column.
- **Dropping unnecessary columns:**  
  Columns like `value` and others are dropped after extraction.
- **Handling missing values:**  
  Null values in important columns (like `gender` and `income`) are dropped.

### 4. Data Transformation

- **Merging datasets:**  
  The notebook merges `events`, `offers`, and `customers` to create a comprehensive dataset.
- **Encoding categorical data:**  
  The `channels` column (a list of channels per offer) is transformed using `MultiLabelBinarizer` to create binary columns for each channel.
- **Renaming columns:**  
  Columns are renamed for clarity (e.g., `difficulty` to `minAmountToCompleteOfferIn$`).

### 5. Requirements

Install the following Python packages if you haven't already:

```bash
pip install pandas numpy seaborn matplotlib plotly scikit-learn
```

### 6. Running the Notebook

Open `Cleaning&Preparation.ipynb` in Jupyter
