# Syriatel Customer Churn Project

![Visualizations](telcom_image.jpg)

# Project Overview

In the rapidly evolving telecommunications industry, customer retention is crucial for sustaining business growth and profitability. This project aims to develop a predictive model that identifies customers at risk of churning from Syriatel, a leading telecommunications company. Furthermore, we seek to analyze the factors contributing to customer churn in order to develop proactive strategies for reducing churn rates. By adopting a long-term approach, this project aims to enhance customer satisfaction, increase loyalty, and maximize Syriatel's market share.


# Data Understanding
The data used in this project was obtained from https://www.kaggle.com/becksddf/churn-in-telecoms-dataset. Tha data has 3333 entries and 21 columns
This dataset provides information about Syriatel's customers, including various attributes such as call duration, customer service calls, and customer churn status among other attributes.

The target variable in this dataset that we aimed to predict was identified as the churn column.



# Data Preparation

The dataset used in this project was already preprocessed and cleaned, requiring no further handling of missing values, outliers, or other data quality issue, although One specific preprocessing step involved removing the phone number column from the dataset(state). The phone number column was deemed unnecessary for churn analysis as it does not provide any relevant information about customer behavior or contribute to predicting churn.  The data is then split into categorical and numerical variables for analysis.

# Exploratory Data Analysis (EDA)

This  phase revealed valuable insights into the Syriatel Customer Churn dataset, including class imbalance in the target variable, the impact of international plans on churn, the influence of customer service calls, and relationships between total calls, minutes, and charges. These insights informed subsequent analysis and model development in the project.
  # 1 .Univariate Analysis
Analyzing the distribution of the target variable "churn."
Visualizing the count of churned customers by features like international plan, area code, voice mail plan, and customer service calls.
 # 2 .Bivariate Analysis
Analyzing the churn rate based on international plan, area code, voice mail plan, and customer service calls.
Comparing churn rates for different American states.
# 3 .Multivariate Analysis
Analyzing the relationship between total calls, total charges, and time periods (daytime, evening, nighttime).
Analyzing the relationship between total international calls, minutes, and charges.


![Total Calls VS Total Charges](https://github.com/okwarojona/PHASE-3-PROJECT-CUSTOMER-CHURN-PREDICTION/blob/master/totalcallls%20vs%20tota%3B_charges.png)



# Preprocessing

In this section, we perform data preprocessing steps to prepare the dataset for model training.

We begin by making a copy of the churn dataset and view its contents.

  #  Feature Engineering
We perform the following steps:

Convert the 'churn' column from boolean to integer for modeling purposes.
Drop the 'state' column as it is not relevant for our modeling.
Create dummy variables for categorical features like 'international plan' and 'voice mail plan'.

We define the predictor variables (X) and target variable (y) for our machine learning models. We also split the data into training and testing sets.


We notice class imbalance in the target variable 'churn.' To address this, we use SMOTE (Synthetic Minority Over-sampling Technique) to resample and balance the classes.
# Modeling
In this section, we build machine learning models to predict customer churn. We use the following algorithms:

* Logistic Regression
* Decision Tree
* Random Forest
* XGBoost
For each model, we fit the data, make predictions, and evaluate the performance using metrics like accuracy, precision, recall, and F1-score.

#### Model Evaluation
* We compare the performance of all the models and select the best-performing ones for further analysis.

##### Model Comparison
* We evaluate the performance of each model and compare their accuracy and recall scores. The models with the highest accuracy and recall are identified.

##### ROC Analysis
* We plot the ROC curves for all classifiers to visualize the performance of the models.

##### Hyperparameter Tuning
* For the best-performing models, we perform hyperparameter tuning to further optimize their performance.

##### Feature Importance
* We identify the top features contributing to customer churn using feature importances from the models.
   
 ![Top 10 Feature Importances in RandomForestClassifier Model](https://github.com/okwarojona/PHASE-3-PROJECT-CUSTOMER-CHURN-PREDICTION/blob/master/Top%2010%20Feature%20Importances%20in%20RandomForestClassifier%20Model.png)  
   
The best model for this dataset is the Tuned RandomForestClassifier with the following parameters:

- max_depth=10, 
- min_samples_leaf=1, 
- min_samples_split=2,
- n_estimators=200,
- random_state=42

# Summary Findings

- Voicemail Plan: Majority of churned customers didn't have a voicemail plan.

- High Call Volume: Churned customers had the highest call volume (up to 9 calls).

- Churn Rates by State: California and New Jersey had churn rates exceeding 25%.

- Day Minutes: Churned customers had higher day minute usage and charges.

- Daytime Charges: Daytime call charges were significantly higher than evening and nighttime charges.

- International Plan: Customers with international plans had higher churn rates despite fewer international calls.


# Conclusion
- Majority of customers who terminated their contracts did not have a voicemail plan.
- California and New Jersey have the highest churn rates, both exceeding 25%
- Customers who terminated their accounts appeared to have subscribed to more day minutes, resulting in higher charges.
- Charges for total daytime calls and minutes were significantly higher compared to evening and nighttime calls and minutes.
- There is a lack of proportionality between the total number of international calls made and the corresponding charges, meaning that charges are higher even with fewer total calls.
- The customers with international plan have the higher churn rate compared to those with no plan
# Future Work

- Real-Time Analysis: Implement real-time churn monitoring and analysis to promptly identify and address potential churn risks, allowing for timely intervention.
- Market Research: Conduct market research to stay updated on industry trends, customer preferences, and competitive offerings, ensuring the company remains responsive to evolving market dynamics.
- Customer Feedback Analysis: Analyze customer feedback, including surveys and social media interactions, to gain valuable insights into customer sentiments and pain points. Utilize this feedback to improve service offerings and customer experience.


