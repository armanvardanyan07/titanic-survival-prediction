````md
# 🚢 Titanic Survival Prediction

An end-to-end machine learning project for the famous Kaggle Titanic competition.

The objective of this project is to predict whether a passenger survived the Titanic disaster using demographic and passenger-related information such as age, gender, ticket class, fare, family size, and cabin data.

---

# 🔗 Kaggle Competition

https://www.kaggle.com/competitions/titanic/

---

# 📌 Project Overview

This repository contains a complete machine learning workflow including:

- Data preprocessing
- Missing value handling
- Feature engineering
- Feature scaling
- Categorical encoding
- Logistic Regression pipeline
- Hyperparameter tuning using GridSearchCV
- Prediction generation
- Kaggle submission creation

The project was created as a practical introduction to supervised machine learning and tabular data classification.

---

# 📂 Repository Structure

```bash
.
├── train.csv
├── test.csv
├── Titanic.ipynb
└── README.md
````

---

# 📊 Dataset Information

The dataset contains passenger information from the Titanic ship disaster.

## Features

| Feature     | Description                       |
| ----------- | --------------------------------- |
| PassengerId | Unique passenger identifier       |
| Pclass      | Ticket class                      |
| Name        | Passenger name                    |
| Sex         | Gender                            |
| Age         | Passenger age                     |
| SibSp       | Number of siblings/spouses aboard |
| Parch       | Number of parents/children aboard |
| Ticket      | Ticket number                     |
| Fare        | Ticket fare                       |
| Cabin       | Cabin number                      |
| Embarked    | Port of embarkation               |

## Target

| Column   | Description                       |
| -------- | --------------------------------- |
| Survived | 0 = Did not survive, 1 = Survived |

---

# ⚙️ Data Preprocessing

Several preprocessing techniques were applied before training the model.

## Missing Values

### Age

Missing age values were replaced using the median age.

### Fare

Missing fare values were filled with the median fare.

### Embarked

Missing embarkation values were replaced using the most common category.

### Cabin

Missing cabin values were replaced with `"Unknown"`.

---

# 🧠 Feature Engineering

Additional features were created to improve model performance.

## FamilySize

```python
FamilySize = SibSp + Parch + 1
```

Represents total family members aboard.

---

## IsAlone

```python
IsAlone = 1 if FamilySize == 1 else 0
```

Indicates whether the passenger traveled alone.

---

## Cabin Extraction

Only the first cabin letter was used:

```python
Cabin = Cabin.str[0]
```

This helps preserve deck-related information while reducing noise.

---

# 🤖 Machine Learning Pipeline

The project uses a Scikit-Learn pipeline consisting of:

* StandardScaler
* LogisticRegression

Pipeline example:

```python
pipe = Pipeline([
    ('scaler', scaler),
    ('model', model)
])
```

---

# 🔍 Hyperparameter Optimization

GridSearchCV was used to find the best parameters.

## Tuned Parameters

* Solver
* Penalty
* Regularization strength (`C`)
* Class weights
* Tolerance values
* ElasticNet ratio

Example:

```python
GridSearchCV(
    pipe,
    params,
    cv=5,
    scoring="accuracy",
    n_jobs=-1
)
```

---

# 📈 Model Performance

The model achieves a solid beginner-level Kaggle score and demonstrates understanding of:

* Supervised learning
* Data preprocessing
* Model optimization
* Cross-validation
* ML pipelines

---

# 🚀 How To Run

## Install Dependencies

```bash
pip install numpy pandas scikit-learn
```

---

## Run Jupyter Notebook

```bash
jupyter notebook
```

Open the notebook and run all cells.

---

# 📦 Output

The generated submission file:

```bash
titan.csv
```

Submission format:

```csv
PassengerId,Survived
892,0
893,1
894,0
```

---

# 🛠 Technologies Used

* Python
* NumPy
* Pandas
* Scikit-Learn
* Jupyter Notebook

---

# 📚 Machine Learning Concepts Used

* Logistic Regression
* Feature Engineering
* Standardization
* Hyperparameter Tuning
* Cross Validation
* Classification

---

# 🎯 Goals Of The Project

* Practice machine learning fundamentals
* Learn tabular data preprocessing
* Understand classification workflows
* Build a reproducible ML pipeline
* Participate in Kaggle competitions

---

# 📌 Future Improvements

Potential future improvements for this project:

* One-Hot Encoding
* Advanced feature engineering
* Ensemble models
* Gradient Boosting
* XGBoost / LightGBM
* Better cross-validation strategies

---

# 🧪 Example Code

```python
grid.fit(X, y)

y_pred = grid.predict(X_test)

submission = pd.DataFrame({
    'PassengerId': df_test['PassengerId'],
    'Survived': y_pred
})

submission.to_csv('titan.csv', index=False)
```

---

# 👨‍💻 Author

Machine learning beginner project focused on practical Kaggle experience and improving data science skills.

---

# ⭐ If You Like This Project

Feel free to star the repository and explore the code.

```
```
