# Food Security Classification Project

## Overview
This project analyzes global food security data and builds a machine learning model to classify countries into different food security categories based on various food-related indicators. The model predicts food security levels using logistic regression and can help identify countries at risk of food insecurity.

## Problem Statement
Food security is a critical global issue that affects millions of people worldwide. This project aims to:
- Analyze food security patterns across different countries and years
- Build a predictive model to classify food security levels
- Identify key indicators that contribute to food insecurity

## Dataset
The project uses the Food Security Data from FAO (Food and Agriculture Organization), which includes:
- **Main Dataset**: `Food_Security_Data_E_All_Data_(Normalized).csv`
- **Supporting Files**:
  - Area codes mapping
  - Element descriptions
  - Item codes
  - Flag definitions

### Key Features
- Country-level food security indicators
- Time series data across multiple years
- Various food production, availability, and nutrition metrics

## Target Variable
The model classifies countries into three food security categories based on the "Prevalence of undernourishment (percent) (3-year average)":

- **Low Risk (0)**: < 5% undernourishment
- **Medium Risk (1)**: 5-15% undernourishment  
- **High Risk (2)**: > 15% undernourishment

## Project Workflow

### 1. Data Loading and Exploration
- Import required libraries (pandas, seaborn, sklearn)
- Load the main dataset with proper data type handling
- Explore data structure and characteristics

### 2. Data Preprocessing
- **Pivot Transformation**: Restructure data with countries and years as rows, food indicators as columns
- **Missing Value Analysis**: Identify columns with >70% missing data and remove them
- **Imputation**: Fill remaining missing values with country-specific means
- **Data Cleaning**: Remove rows with remaining null values

### 3. Feature Engineering
- Convert undernourishment percentages to categorical food security levels
- Remove target variable and non-predictive columns (Area Code, Year)
- Feature scaling using StandardScaler for optimal model performance

### 4. Model Development
- **Algorithm**: Logistic Regression
- **Train-Test Split**: 70-30 split with random state for reproducibility
- **Scaling**: StandardScaler applied to all features

### 5. Model Evaluation
- Accuracy score calculation
- Detailed classification report with precision, recall, and F1-score

## Key Libraries Used
- **pandas**: Data manipulation and analysis
- **seaborn**: Data visualization
- **scikit-learn**: Machine learning algorithms and preprocessing
  - `StandardScaler`: Feature scaling
  - `train_test_split`: Data splitting
  - `LogisticRegression`: Classification algorithm
  - `accuracy_score`, `classification_report`: Model evaluation

## File Structure
```
foodClassification/
│
├── AppFinal.ipynb                              # Main Jupyter notebook
├── README.md                                   # Project documentation
├── Descriptions_and_Metadata.xlsx             # Dataset metadata
│
└── Food_Security_Data_E_All_Data_(Normalized)/
    ├── Food_Security_Data_E_All_Data_(Normalized).csv
    ├── Food_Security_Data_E_AreaCodes.csv
    ├── Food_Security_Data_E_Elements.csv
    ├── Food_Security_Data_E_Flags.csv
    └── Food_Security_Data_E_ItemCodes.csv
```

## How to Run the Project

### Prerequisites
```bash
pip install pandas seaborn scikit-learn matplotlib jupyter
```

### Execution Steps
1. Clone the repository
2. Ensure all data files are in the correct directory structure
3. Open `AppFinal.ipynb` in Jupyter Notebook or VS Code
4. Run all cells sequentially

## Results
The logistic regression model successfully classifies countries into food security categories. The model provides:
- Accuracy score for overall performance
- Detailed classification metrics for each security level
- Insights into which food indicators are most predictive of food insecurity

## Key Insights
- Successfully transformed complex time-series food data into a classification problem
- Demonstrated effective handling of missing data using country-specific imputation
- Created a practical tool for identifying countries at different levels of food security risk

## Future Improvements
- Experiment with other classification algorithms (Random Forest, SVM, etc.)
- Include time-based features to capture trends
- Add cross-validation for more robust model evaluation
- Implement feature importance analysis to identify key indicators
- Create visualization dashboards for better insights

## Contributing
Feel free to fork this project and submit pull requests for improvements. Areas for contribution include:
- Additional preprocessing techniques
- Alternative machine learning algorithms
- Enhanced visualization and reporting
- Performance optimization

## License
This project is open source and available under the MIT License.

## Contact
For questions or collaboration opportunities, please feel free to reach out through GitHub issues.
