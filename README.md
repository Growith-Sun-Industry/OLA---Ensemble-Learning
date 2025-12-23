# Ola Driver Attrition Prediction – Case Study

## Problem Statement

Recruiting and retaining drivers is considered a major challenge for Ola. **Driver churn is high**, and drivers can easily stop working for Ola or switch to competitors like Uber depending on incentives and rates.

As the company scales, high churn becomes an even bigger concern. To onboard new drivers, Ola casts a wide net, including individuals who do not already own cars. However, this acquisition strategy is **costly**, and frequent driver attrition negatively impacts organizational morale. Moreover, **acquiring new drivers is significantly more expensive than retaining existing ones**.

You are working as a **Data Scientist** in the **Analytics Department of Ola**, focusing on **driver attrition**. You are provided with **monthly data for a segment of drivers from 2019 and 2020** and are tasked with predicting **whether a driver will leave the company** based on:

- **Demographics:** City, age, gender, etc.  
- **Tenure Information:** Date of joining, last working date  
- **Performance History:** Quarterly rating, monthly business acquired, grade, income  

---

## Dataset

- **Dataset Name:** `ola_driver.csv`  
- **Dataset Link:** `ola_driver.csv`

---

## Column Profiling

| Column Name | Description |
|------------|------------|
| `MMMM-YY` | Reporting month and year |
| `Driver_ID` | Unique identifier for drivers |
| `Age` | Age of the driver |
| `Gender` | Gender (Male = 0, Female = 1) |
| `City` | City code of the driver |
| `Education_Level` | Education level (0 = 10+, 1 = 12+, 2 = Graduate) |
| `Income` | Monthly average income |
| `DateOfJoining` | Joining date of the driver |
| `LastWorkingDate` | Last working date of the driver |
| `JoiningDesignation` | Designation at the time of joining |
| `Grade` | Driver grade at the time of reporting |
| `TotalBusinessValue` | Total business value generated in a month |
| `QuarterlyRating` | Quarterly driver rating (1–5, higher is better) |

---

## Concepts Tested

- Ensemble Learning – **Bagging**
- Ensemble Learning – **Boosting**
- **KNN Imputation** for missing values
- Handling **Imbalanced Datasets**

---

## What “Good” Looks Like

### 1. Data Understanding & Preparation
- Import the dataset and examine its structure and characteristics  
- Convert **date-like features** to appropriate datetime formats  
- Check for missing values and prepare data for **KNN Imputation**  
  - Consider **only numerical features** for imputation  

---

### 2. Data Aggregation
- Aggregate data to remove **multiple records per driver**  
- Start with unique `Driver_ID`s and bring all features to the same level  
- Group data using `Driver_ID` (similar to the Delhivery case study)

---

### 3. Feature Engineering
- Create a feature indicating whether **Quarterly Rating increased**  
  - Assign `1` if increased, else `0`  
- Create the **target variable**:
  - `1` if `LastWorkingDate` is present (driver left)  
  - `0` otherwise  
- Create a feature indicating whether **Monthly Income increased**  
  - Assign `1` if increased, else `0`  

---

### 4. Exploratory & Statistical Analysis
- Generate statistical summary of the derived dataset  
- Analyze **correlation** among independent variables  
- Understand interactions between features  

---

### 5. Data Preprocessing
- Perform **One-Hot Encoding** for categorical variables  
- Handle **class imbalance** using appropriate techniques  
- Apply **standardization** on training data  

---

### 6. Model Building
- Apply **Ensemble Learning techniques**:
  - Bagging methods  
  - Boosting methods  
- Perform **hyperparameter tuning** to optimize performance  

---

## Results Evaluation

- Classification Report  
- ROC–AUC Curve  

---

## Final Deliverables

- A robust attrition prediction model  
- Clear interpretation of key drivers of churn  
- **Actionable insights & business recommendations** to improve driver retention
