# 🩺 TASK-3 - Feature Engineering, Encoding & Model Building for Diabetes Dataset

## VAUTECH IT SOLUTIONS - TASK 3

|             |                                                         |
| ----------- | ------------------------------------------------------- |
| **Intern**  | Ved Ingole                                              |
| **Domain**  | Machine Learning                                        |
| **Company** | VAUTECH IT SOLUTIONS                                    |
| **Task**    | Feature Engineering, Encoding, Scaling & Model Building |

---

# 📂 Dataset

* **Dataset Name:** PIMA Indians Diabetes Dataset
* **Source:** OpenML Repository
* **Loaded Using:** `fetch_openml()` from scikit-learn
* **Instances:** 768
* **Features:** 8 Input Features + 1 Target Column
* **Task Type:** Binary Classification
* **Target:** `0 = No Diabetes` / `1 = Diabetes`

---

# 🎯 Project Objectives

1. Perform feature engineering on medical data
2. Create meaningful derived features
3. Apply categorical feature encoding
4. Scale numerical features
5. Split dataset into training and testing sets
6. Train a Machine Learning model
7. Evaluate model performance
8. Analyze feature importance

---

# 🔁 Project Pipeline

## Step 1: Load Dataset

* Loaded PIMA Indians Diabetes Dataset using `fetch_openml()`
* Converted target labels into numeric values
* Renamed feature columns for better readability

Features:

* Pregnancies
* Glucose
* BloodPressure
* SkinThickness
* Insulin
* BMI
* DiabetesPedigreeFunction
* Age
* Target

---

## Step 2: Data Cleaning

* Identified medically invalid zero values
* Replaced invalid values with `NaN`
* Applied median imputation for missing values

Columns cleaned:

* Glucose
* BloodPressure
* SkinThickness
* Insulin
* BMI

---

## Step 3: Feature Engineering

Created several new features to improve predictive power.

### BMI Category

Patients categorized as:

* Underweight
* Normal
* Overweight
* Obese

### Age Group

Age divided into:

* Young
* Middle
* Senior
* Elderly

### Glucose Risk

Risk groups:

* Normal
* Prediabetes
* Diabetes

### Ratio Features

Created:

* Insulin_Glucose_Ratio
* Skin_BMI_Ratio

### Interaction Features

Created:

* BMI_Age_Interaction

### Binary Flags

Created:

* High_Pedigree
* High_Pregnancies

---

## Step 4: Feature Encoding

Applied encoding techniques for categorical features.

### Ordinal Encoding

Encoded:

* BMI_Category
* Age_Group
* Glucose_Risk

### One-Hot Encoding

Created dummy variables for:

* Region

Generated:

* Region_Urban
* Region_Suburban
* Region_Rural

---

## Step 5: Feature Scaling

Applied:

### StandardScaler

Standardized numerical features by:

* Removing mean
* Scaling to unit variance

Benefits:

* Improved model performance
* Consistent feature magnitudes
* Better learning behavior

---

## Step 6: Train-Test Split

Dataset divided into:

* Training Data: 80%
* Testing Data: 20%

Parameters used:

* `test_size = 0.20`
* `random_state = 42`
* `stratify = target`

---

## Step 7: Model Training

### Algorithm Used

Random Forest Classifier

Configuration:

* `n_estimators = 200`
* `random_state = 42`

Model trained using processed training dataset.

---

## Step 8: Model Evaluation

Performance metrics used:

* Accuracy Score
* Precision
* Recall
* F1-Score
* Classification Report

Evaluation performed on unseen test data.

---

## Step 9: Feature Importance Analysis

Random Forest feature importance scores were extracted.

Purpose:

* Identify influential predictors
* Understand model decisions
* Detect dominant medical factors

Top contributing features typically include:

* Glucose
* BMI
* Age
* DiabetesPedigreeFunction
* Insulin

---

## Step 10: Visualization

Generated visualization:

### Feature Importance Graph

Visualized:

* Top 10 Important Features

Benefits:

* Easy interpretation
* Feature ranking
* Model explainability

Output File:

```text
outputs/feature_importance.png
```

---

# 📊 Key Findings

| Analysis               | Observation                     |
| ---------------------- | ------------------------------- |
| Most Important Feature | Glucose                         |
| Strong Predictors      | BMI, Age, Diabetes Pedigree     |
| Model Used             | Random Forest Classifier        |
| Feature Engineering    | Improved dataset representation |
| Evaluation Method      | Train-Test Split                |

---

# 🛠️ Tools & Libraries

| Tool         | Purpose                          |
| ------------ | -------------------------------- |
| Python       | Programming Language             |
| pandas       | Data Manipulation                |
| NumPy        | Numerical Operations             |
| matplotlib   | Visualization                    |
| seaborn      | Statistical Visualization        |
| scikit-learn | Preprocessing & Machine Learning |

---

# 📁 Files

| File                           | Description                      |
| ------------------------------ | -------------------------------- |
| `task3_feature_engineering.py` | Main Python Script               |
| `README.md`                    | Project Documentation            |
| `feature_importance.png`       | Feature Importance Visualization |
| `outputs/`                     | Saved Output Files               |

---

# 📈 Visualizations Included

* Top 10 Feature Importance Graph

---

# 📚 Dataset Citation

Smith, J. W., Everhart, J. E., Dickson, W. C., Knowler, W. C., & Johannes, R. S. (1988). PIMA Indians Diabetes Dataset. National Institute of Diabetes and Digestive and Kidney Diseases.

---

# 👨‍💻 Author

Ved Ingole

---

# ✅ Conclusion

This project focused on advanced data preprocessing techniques including feature engineering, encoding, feature scaling, model training, and feature importance analysis. The Random Forest model was trained on the transformed dataset and used to identify the most influential factors contributing to diabetes prediction. The project provided practical experience in preparing real-world healthcare data for machine learning applications.
