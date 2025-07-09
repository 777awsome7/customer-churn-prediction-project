# Customer Churn Prediction and Data Quality Analysis

---

## Problem Statement

This project aims to demonstrate fundamental data science and machine learning skills by addressing a common business problem: **customer churn**. Customer churn, or customer attrition, refers to the rate at which customers stop doing business with an entity. Predicting churn allows businesses to proactively identify at-risk customers and implement retention strategies, which is often more cost-effective than acquiring new customers.

Specifically, this project involves:
1.  Performing essential data cleaning and preparation on a raw customer dataset.
2.  Building and training a basic machine learning model (Logistic Regression) to predict whether a customer is likely to churn.
3.  Evaluating the model's performance on unseen data.

This project serves as a foundational portfolio piece, showcasing practical skills in data handling, basic machine learning model development, and results interpretation.

---

## Data Description

The dataset used in this project is a mock customer dataset containing 8 entries (rows) and 6 features (columns). Each row represents a unique customer with attributes such as:

* `customer_id`: Unique identifier for each customer.
* `age`: Age of the customer.
* `gender`: Gender of the customer (categorical: Female/Male).
* `annual_income`: Customer's annual income.
* `has_loyalty_card`: Boolean indicating if the customer has a loyalty card.
* `last_purchase_amount`: Amount of the customer's last purchase.

Initial inspection revealed missing values in the `age`, `annual_income` (initially represented as 'null' string), and `last_purchase_amount` columns, which required cleaning. A synthetic `churn` column was added to enable predictive modeling.

---

## Data Cleaning Steps

Real-world data is rarely perfect and often contains missing values or inconsistencies. For this project, the following data cleaning strategies were applied:

1.  **Dropped rows with missing `age`:** Rows where the `age` information was entirely absent were removed.
2.  **Filled missing `annual_income` values:** Missing entries in the `annual_income` column were imputed (filled) with the **mean** of the existing annual incomes.
3.  **Filled missing `last_purchase_amount` values:** Missing values in `last_purchase_amount` were filled with `0`.
4.  **Handled Categorical Data (`gender`):** The `gender` column (Female/Male) was converted into a numerical format using **Label Encoding** (Female: 0, Male: 1).

---

## Model Building: Logistic Regression

For this binary classification problem (predicting churn: Yes/No), **Logistic Regression** was chosen as the machine learning algorithm.

* **Logistic Regression** is a fundamental and widely used statistical model for binary classification. It estimates the probability of an instance belonging to a particular class.

The data was split into training (80%) and testing (20%) sets to ensure the model's performance is evaluated on unseen data. Numerical features were scaled using `StandardScaler` to normalize their ranges, which helps the Logistic Regression algorithm converge faster and perform optimally. The model was initialized with `random_state` for reproducibility and `max_iter` was increased to ensure the optimization process converged.

---

## Results and Insights

After training the Logistic Regression model, its performance on the unseen test set was evaluated.

* **Sample Prediction:** The model successfully made a prediction for a sample customer in the test set.
* **Overall Model Performance (Accuracy & Classification Report):** Metrics like accuracy, precision, recall, and F1-score were used to assess how well the model performed. (Note: Due to the very small size of this mock dataset, the accuracy and classification report may show extreme values or appear trivial. In real-world scenarios, these metrics are crucial for understanding a model's strengths and weaknesses.)

This project demonstrates the ability to build and evaluate a basic predictive model from raw data.

---

## Future Work/Improvements

This project provides a foundational understanding. For a more robust and production-ready solution, several improvements could be considered:

* **More Data:** Real-world datasets are much larger and more diverse.
* **Feature Engineering:** Creating new, more informative features from existing ones.
* **Advanced Data Cleaning:** Handling outliers, more sophisticated imputation methods.
* **Other Models:** Experimenting with different machine learning algorithms.
* **Hyperparameter Tuning:** Optimizing the settings of the chosen model.
* **Cross-Validation:** A more robust method for evaluating model performance on small datasets.
* **Deployment:** Turning the model into an API or integrating it into a business application.

---

[View Jupyter Notebook on GitHub](customer_churn_prediction.ipynb)