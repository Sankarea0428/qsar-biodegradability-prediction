# QSAR Biodegradability Prediction with Exploratory Data Analysis and Baseline Machine Learning

## Project Overview

This project investigates whether precomputed molecular descriptors can be used to predict whether a chemical compound is readily biodegradable. Using the QSAR biodegradation dataset, the project combines exploratory data analysis, baseline machine learning models, error analysis, feature importance analysis, and simple improvement experiments in Python.

The goal of the project is not only to build baseline classifiers, but also to understand which descriptors are useful, how model performance changes under different evaluation priorities, and how exploratory findings align with model-based interpretation.

---

## Dataset

The project uses the **QSAR biodegradation dataset**, which contains:

- **1055 compounds**
- **41 molecular descriptors**
- a binary target indicating whether a compound is:
  - **RB**: readily biodegradable
  - **NRB**: not readily biodegradable

During preprocessing, the original numeric labels were remapped to descriptive class names for clearer interpretation.

---

## Methods

The project was completed in four main stages:

### 1. Exploratory Data Analysis (EDA)
- class distribution analysis
- descriptive statistics
- boxplots of interpretable descriptors
- grouped mean/median comparison
- correlation analysis
- preliminary feature screening

### 2. Baseline Modeling
- Logistic Regression
- Decision Tree
- Random Forest

### 3. Model Interpretation
- confusion-matrix-based error analysis
- Random Forest feature importance
- comparison between EDA-based screening and model-based important features

### 4. Improvement Experiments
- Scaled Logistic Regression
- Balanced Logistic Regression

---

## Key Results

- **Random Forest** achieved the strongest overall classification performance.
- **Balanced Logistic Regression** achieved the highest recall for the **RB** class.
- Several interpretable descriptors, such as **nO**, **nN**, **nX**, and **C%**, showed meaningful class-related differences in EDA.
- Model-based feature importance highlighted several abstract QSAR descriptors, including **SpMax_B(m)**, **SM6_B(m)**, **SpMax_L**, and **SpPosA_B(p)**.
- There was strong overlap between EDA-based candidate features and Random Forest top features, suggesting good consistency between exploratory analysis and model-based interpretation.

---

## Model Comparison Highlights

The final model comparison showed a clear trade-off between **overall accuracy** and **RB-class sensitivity**:

- **Random Forest** achieved the highest overall accuracy.
- **Balanced Logistic Regression** achieved the highest recall for the RB class.
- **Scaled Logistic Regression** slightly improved overall Logistic Regression accuracy, but did not improve RB recall.
- **Decision Tree** showed the weakest overall performance among the tested models.

This means that the most suitable model depends on the evaluation priority:
- if **overall classification performance** is more important, **Random Forest** is preferable;
- if **identifying as many RB compounds as possible** is more important, **Balanced Logistic Regression** is preferable.

---

## Visual Comparison

### Model Accuracy Comparison
![Model Accuracy Comparison](figures/model_accuracy_comparison.png)

### Model Recall for RB Class
![Model Recall for RB Class](figures/model_recall_rb.png)

---

## Project Structure

- `notebooks/01_qsar_eda.ipynb` — exploratory data analysis
- `notebooks/02_qsar_modeling.ipynb` — baseline models and improvement experiments
- `notebooks/03_report_draft.ipynb` — report-style project write-up
- `figures/` — saved plots and visual outputs
- `report/` — report-related materials
- `requirements.txt` — project dependencies

---

## Main Conclusion

Biodegradability prediction depends on a combination of molecular descriptors rather than any single feature alone. Different models perform best under different evaluation priorities: **Random Forest** is strongest overall, while **Balanced Logistic Regression** is most effective when recall for the RB class is especially important.

---

## Tools and Libraries

- Python
- pandas
- numpy
- matplotlib
- scikit-learn
- Jupyter Notebook

---

## Future Improvement Directions

Possible next steps include:

- hyperparameter tuning for baseline models
- stronger validation strategies
- feature selection for a smaller descriptor subset
- alternative molecular representations
- deeper chemical interpretation of important descriptors

---

## Author

This project was developed as a Python-based machine learning and scientific data analysis project on QSAR biodegradability prediction.
