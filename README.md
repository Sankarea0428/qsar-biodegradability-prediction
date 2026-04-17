\# QSAR Biodegradability Prediction with Exploratory Data Analysis and Baseline Machine Learning



\## Project Overview

This project investigates whether precomputed molecular descriptors can be used to predict whether a chemical compound is readily biodegradable. Using the QSAR biodegradation dataset, the project combines exploratory data analysis, baseline machine learning models, error analysis, feature importance analysis, and simple improvement experiments.



\## Dataset

The project uses the QSAR biodegradation dataset, which contains:

\- 1055 compounds

\- 41 molecular descriptors

\- a binary target indicating whether a compound is readily biodegradable (RB) or not readily biodegradable (NRB)



The original labels were remapped from numeric codes to descriptive class names during preprocessing.



\## Methods

The project was completed in several stages:



1\. \*\*Exploratory Data Analysis\*\*

&#x20;  - class distribution analysis

&#x20;  - descriptive statistics

&#x20;  - boxplots of interpretable descriptors

&#x20;  - grouped mean/median comparison

&#x20;  - correlation analysis

&#x20;  - preliminary feature screening



2\. \*\*Baseline Modeling\*\*

&#x20;  - Logistic Regression

&#x20;  - Decision Tree

&#x20;  - Random Forest



3\. \*\*Model Interpretation\*\*

&#x20;  - confusion-matrix-based error analysis

&#x20;  - Random Forest feature importance

&#x20;  - comparison between EDA-based screening and model-based importance



4\. \*\*Improvement Experiments\*\*

&#x20;  - Scaled Logistic Regression

&#x20;  - Balanced Logistic Regression



\## Key Results

\- Random Forest achieved the strongest overall classification performance.

\- Balanced Logistic Regression achieved the highest recall for the RB class.

\- Several interpretable descriptors, such as nO, nN, nX, and C%, showed meaningful class-related differences in EDA.

\- Model-based feature importance highlighted several abstract QSAR descriptors, including SpMax\_B(m), SM6\_B(m), SpMax\_L, and SpPosA\_B(p).

\- There was strong overlap between EDA-based candidate features and Random Forest top features, suggesting good consistency between exploratory analysis and model-based interpretation.



\## Project Structure

\- `notebooks/01\_qsar\_eda.ipynb` — exploratory data analysis

\- `notebooks/02\_qsar\_modeling.ipynb` — baseline models and improvement experiments

\- `notebooks/03\_report\_draft.ipynb` — project write-up

\- `figures/` — saved plots and visual outputs

\- `report/` — report-related materials



\## Main Conclusion

Biodegradability prediction depends on a combination of molecular descriptors rather than any single feature alone. Different models perform best under different evaluation priorities: Random Forest is strongest overall, while Balanced Logistic Regression is most effective when recall for the RB class is especially important.



\## Tools and Libraries

\- Python

\- pandas

\- numpy

\- matplotlib

\- scikit-learn

\- jupyter

