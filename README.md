# Titanic Survival Prediction (No Pipeline)

This notebook demonstrates a Titanic survival prediction project using a manual approach to preprocessing and modeling **without using scikit-learn Pipelines**. It uses the Titanic dataset from Seaborn.

## Overview

The project performs data cleaning, encoding, and model training step-by-step using basic tools and a simple machine learning model — `DecisionTreeClassifier`. It shows how you can preprocess data manually and train a model with custom handling for categorical and missing values.

---

## 📂 Steps Performed

### 1. Load Dataset

* Used `seaborn`'s built-in Titanic dataset.

### 2. Data Cleaning

* Dropped irrelevant or redundant columns:

  ```
  ['class', 'who', 'adult_male', 'deck', 'embark_town', 'alive', 'alone']
  ```

### 3. Data Splitting

* Split into training and testing using `train_test_split`.

### 4. Handling Missing Values

* Used `SimpleImputer`:

  * Mean imputation for `age`
  * Most frequent imputation for `embarked`

### 5. Encoding Categorical Variables

* Applied `OneHotEncoder` (with `handle_unknown='ignore'`) for:

  * `sex`
  * `embarked`

### 6. Final Feature Preparation

* Concatenated the transformed categorical and numeric columns manually using `numpy.concatenate`.

### 7. Model Training

* Trained a `DecisionTreeClassifier` on the transformed training data.
* Evaluated performance using `accuracy_score` on test data.

### 8. Model Saving

* Saved the trained model and encoders using `pickle`:

  * `clf.pkl`
  * `ohe_sex.pkl`
  * `ohe_embarked.pkl`

---

## Requirements

```bash
pandas
numpy
seaborn
scikit-learn
pickle
```

## Usage

1. Clone or download the repository.
2. Open and run the notebook `titanic_wihtoutpipeline.ipynb` step-by-step in Jupyter Notebook.

## Notes

* This version skips the use of `Pipeline` for clarity and educational value.
* It can be further improved with validation techniques and hyperparameter tuning.

## License

MIT License
