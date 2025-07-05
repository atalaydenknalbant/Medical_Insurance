# Medical Insurance Cost Prediction

This project analyzes medical insurance data and builds regression models to estimate an individual’s annual insurance charge based on personal and health factors

## Overview

This work uses a data set of 1338 records with seven attributes  
- Age (in years)
- Sex (female or male)
- BMI (body mass index)
- Children (number of dependents)
- Smoker (yes or no)
- Region (northeast, northwest, southeast, southwest)
- Charges (annual medical cost in USD)

Models trained include  
* Linear regression  
* Polynomial regression of degree two  
* Random forest regression  

Model performance is compared using mean absolute error mean squared error and root mean squared error

## Setup

1. Clone this repository to your local machine  
2. Ensure you have Python version three point eight or higher installed  
3. Place the file insurance.csv in the project root folder  
4. Create and activate a virtual environment if desired  

## Dependencies

Run this command in your project folder to install all required libraries  
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

## Usage

First start a Jupyter server in the project folder  
```bash
jupyter notebook
```  
Then open the file Medical_Insurance_Cost_Prediction.ipynb and execute all cells in order

## Project Workflow

1. Load the data from insurance.csv  
2. Check for missing values  
3. Encode categorical fields sex smoker and region using label encoding  
4. Explore distributions and relationships with plots and a correlation heat map  
5. Split data into training and hold-out sets  
6. Train linear regression polynomial regression and random forest models  
7. Evaluate each model on hold-out data using MAE MSE and RMSE  
8. Compare results and choose the best performing model  
9. Use the chosen model to predict charges for new input records

## File Structure

```text
Medical_Insurance
* Medical_Insurance_Cost_Prediction.ipynb   notebook containing code and analysis
* insurance.csv                             raw data file
```

## Example Prediction

At the end of the notebook you can supply a new record to get an estimated annual charge  
```python
import pandas as pd
from sklearn.linear_model import LinearRegression

# code from notebook that trains model and encoders
model = LinearRegression().fit(X_train, y_train)

new_data = pd.DataFrame({
    'age': [30],
    'sex': [1],        # 1 for male 0 for female
    'bmi': [24.5],
    'children': [2],
    'smoker': [0],     # 1 for yes 0 for no
    'region': [2]      # coded regions match notebook encoding
})

estimate = model.predict(new_data)[0]
print(estimate)
```

## Source

Google Drive data set link
https://drive.google.com/file/d/1rJNN5oWWXtWnY_MAdYnOE-tI_lpyXQc5/view

