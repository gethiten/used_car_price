# What Drives the Price of a Used Car?

## Project Overview

This notebook explores a dataset of used cars to understand the key factors that influence their prices. The goal is to provide insights and recommendations to a used car dealership to help them optimize their inventory and pricing strategies. The project follows the CRISP-DM methodology, progressing through business understanding, data understanding, data preparation, modeling, evaluation, and deployment phases.

## Dataset

The dataset used in this project is sourced from Kaggle and contains information on over 426,000 used cars and 18 columns with attributes, including: Manufacturer(Make), Model, Price, odometer, cylinders, etc. 

## Methodology

The project follows the standard [(CRISP-DM framework)](https://github.com/gethiten/used_car_price/tree/main/images/crisp.png) :

1.  **Business Understanding:** Defining the problem of identifying key price drivers for used cars from a business perspective and reframing it as a data science task (supervised regression).
2.  **Data Understanding:** Initial exploration of the dataset, including inspecting data types, summary statistics, checking for missing values, duplicates, and outliers, and visualizing distributions and relationships between features.
3.  **Data Preparation:** Cleaning and transforming the data to prepare it for modeling. This involved handling missing values (imputation and dropping columns), addressing outliers (log transformations for price and odometer), handling zero values, dealing with high-cardinality categorical features (grouping 'model'), creating new features (car age), and encoding categorical variables (one-hot encoding). The data was then split into training and testing sets.
4.  **Modeling:** Building and training several regression models (Linear Regression, Ridge, Lasso, Gradient Boosting, Random Forest) to predict the log-transformed car price. Pipelines were used to chain preprocessing steps with the models.
5.  **Evaluation:** Evaluating the performance of the trained models and pipelines using metrics such as Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and R-squared. Cross-validation was performed to get robust performance estimates. Hyperparameter tuning was conducted for some models to optimize their performance.
6.  **Deployment:** Summarizing the key findings and recommendations in a report format for the client.

## Key Findings

*   Initial data analysis revealed skewed distributions for price and odometer and significant missing values in several columns.
*   Car age and odometer reading showed a weak negative correlation with price, while the number of cylinders had a weak positive correlation.
*   After preprocessing and modeling, the **Tuned Ridge Regression Pipeline** performed best among the models explored, achieving the lowest RMSE and highest R-squared on the test set (R-squared ~ 0.35).
*   The model indicates that car age and odometer are negatively associated with price, while the number of cylinders has a positive association.
Specific regions, manufacturers, and model groups also have significant impacts on price, as indicated by the model coefficients.
*   The moderate R-squared value suggests that while the model provides valuable insights, other factors not included in the dataset or more complex relationships also influence used car prices.

## Recommendations for the Dealership

*   Focus on acquiring newer cars with lower mileage.
*   Be mindful of regional price variations.
*   Prioritize stocking high-value makes and models identified through the analysis.
*   Acknowledge that other factors, beyond those included in the model, also influence price.
*   Consider further data collection and analysis for deeper insights.

## Repository Contents:
    
  *  data: Contains the dataset used in the analysis [vehicles.csv](https://github.com/gethiten/used_car_price/tree/main/data/).
  *  used_car_price_prediction.ipynb: Jupyter Notebook containing the code for data exploration, analysis, and visualization. [used_car_price_prediction.ipynb](https://github.com/gethiten/used_car_price/tree/main/used_car_price_prediction.ipynb)
  *  images/: Folder containing generated visualizations. [Images](https://github.com/gethiten/used_car_price/tree/main/images/)
  *  README.md: This file provides an overview of the project. README.md

## How to Run the Notebook

1.  Ensure you have a Python environment like Google Colab or Jupyter with the necessary libraries installed (pandas, numpy, scikit-learn, matplotlib, seaborn) with the latest versions.
2.  If you are using Jupyter, make sure to have the latest library, as I encountered an error due to different library versions.
3.  I used Google Colab to complete my project.
4.  Upload the notebook file used_car_price.ipynb to your Jupyter environment or open it in your local environment.
5.  Ensure the dataset (`vehicles.csv`) is in the correct location or update the file path in the notebook's data loading cell.
6.  Run each code cell sequentially. The notebook is structured to follow the CRISP-DM steps.
7.  Review the outputs of each cell, including visualizations and printed summaries.
8.  The final markdown cell provides a structured report summarizing the findings and recommendations.

## Dependencies

The main libraries used in this notebook are:

*   pandas
*   numpy
*   scikit-learn
*   matplotlib
*   seaborn

You can install these using pip:
