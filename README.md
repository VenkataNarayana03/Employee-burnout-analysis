# Employee Burnout Analysis

A comprehensive data science project that analyzes employee burnout factors and builds a predictive model to estimate burnout rates.

## Project Overview

This project aims to identify key factors contributing to employee burnout and develop a machine learning model to predict burnout rates. The analysis includes data preprocessing, exploratory data analysis, feature engineering, and predictive modeling using linear regression.

## Dataset

The project uses the `employee_burnout_analysis-AI.xlsx` dataset containing comprehensive employee information for burnout analysis.

### Dataset Features

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| **Employee ID** | Object | Unique identifier for each employee (removed during preprocessing) |
| **Date of Joining** | DateTime | Date when the employee joined the company (converted to numerical features) |
| **Gender** | Object | Gender of the employee (Male/Female) |
| **Company Type** | Object | Type of company (Service/Product) |
| **WFH Setup Available** | Object | Work from home setup availability (Yes/No) |
| **Designation** | Object | Job designation/role of the employee |
| **Resource Allocation** | Numeric | Amount of resources allocated to the employee |
| **Mental Fatigue Score** | Numeric | Self-reported mental fatigue level |
| **Burn Rate** | Numeric | **Target Variable** - Employee burnout rate (0.0 to 1.0) |

### Data Characteristics

- **Missing Values**: Handled by dropping rows with null values
- **Categorical Variables**: Encoded using one-hot encoding
- **Target Variable**: Burn Rate (continuous value between 0 and 1)
- **Feature Types**: Mix of numerical and categorical data

### Feature Engineering Applied

1. **Date Processing**: Converted Date of Joining to numerical representation (days since 2008-01-01)
2. **One-Hot Encoding**: Applied to categorical variables:
   - Company Type → Company Type_Product, Company Type_Service
   - WFH Setup Available → WFH Setup Available_Yes, WFH Setup Available_No
   - Gender → Gender_Male, Gender_Female
3. **Feature Scaling**: StandardScaler applied to all numerical features

## Technologies Used

- **Python** - Programming language
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Matplotlib & Seaborn** - Data visualization
- **Scikit-learn** - Machine learning and preprocessing
- **Jupyter Notebook** - Interactive development environment

## Project Structure

```
employee burn out analysis/
├── employee_burnout_analysis.ipynb    # analysis notebook
├── employee_burnout_analysis-AI.xlsx  # Dataset
└── README.md                          # This file
```

## 🔍 Analysis Pipeline

### 1. Data Loading and Exploration
- Load dataset from Excel file
- Examine data structure, shape, and basic statistics
- Check for missing values and data types

### 2. Data Preprocessing
- Handle missing values by dropping rows with null values
- Remove irrelevant columns (Employee ID)
- Process date features (Date of Joining)
- Encode categorical variables using one-hot encoding

### 3. Exploratory Data Analysis
- Correlation analysis to identify relationships with burnout rate
- Pair plots for visualizing feature relationships
- Distribution analysis of categorical variables
- Hiring patterns analysis by month

### 4. Feature Engineering
- Convert date features to numerical representations
- Apply one-hot encoding to categorical variables:
  - Company Type
  - WFH Setup Available
  - Gender

### 5. Model Development
- Split data into training and testing sets (70/30 ratio)
- Standardize features using StandardScaler
- Train Linear Regression model
- Evaluate model performance using:
  - Mean Squared Error (MSE)
  - Root Mean Squared Error (RMSE)
  - R² Score

## Key Findings

- The dataset contains multiple features correlated with employee burnout
- Categorical variables were successfully encoded for model training
- Linear Regression model provides baseline performance for burnout prediction
- Data preprocessing steps ensure clean, model-ready data

## Getting Started

### Prerequisites
- Python 3.7+
- Jupyter Notebook or JupyterLab
- Required packages (install via pip):

```cmd
pip install numpy pandas matplotlib seaborn scikit-learn openpyxl
```

### Running the Analysis
1. Clone or download this repository
2. Navigate to the project directory
3. Open the Jupyter notebook:
   ```cmd
   jupyter notebook employee_burnout_analysis.ipynb
   ```
4. Run the cells sequentially to reproduce the analysis

## Model Performance

The Linear Regression model achieved the following metrics:
- **Mean Squared Error**: 0.0031
- **Root Mean Squared Error**: 0.0561
- **R² Score**: 0.9188

## Future Improvements

- Try advanced regression models (Random Forest, Gradient Boosting)
- Perform hyperparameter tuning
- Include additional features like work-life balance metrics
- Develop a web application for burnout prediction
- Add cross-validation for more robust evaluation
