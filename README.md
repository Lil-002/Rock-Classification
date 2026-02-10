# Rock-Classification (Machine Learning Project) 

## Overview
Age Classification and Geochemical Prediction of Volcanic Rocks

This project investigates how well different geochemical datasets can be used to 
(1) classify volcanic rock samples into age groups and 
(2) predict rock “maturity” using Mg#. 
The work compares two analytical sources—EMPA and Laser Ablation—to determine which is more suitable for each task.

Two modelling approaches were implemented. For classification, Logistic Regression, Random Forest, and a basic Neural Network were trained to predict three age categories, with F1-score used as the primary metric. For regression, Linear Regression was applied to predict Mg#, evaluated using R². 

Data preparation included handling non-numeric entries, managing values below detection limits using an LOD/2 strategy, removing fully empty Laser rows (which contained ~71% missing data), and performing train–test splitting prior to imputation and scaling to avoid leakage. Median imputation was used to preserve distribution neutrality. 

Exploratory data analysis showed that EMPA element concentrations were largely stable across age groups, producing significant overlap in visualizations and limiting age separability. In contrast, Laser data displayed clearer compositional trends (e.g., V-shaped and inverted V-shaped element patterns), providing stronger signals for distinguishing ages. 

Key findings include:

- Best Classification Performance: Logistic Regression achieved the strongest overall F1-score (0.9735), especially on the combined dataset. 

- Regression Performance: EMPA data produced near-perfect Mg# prediction (R² ≈ 0.995), while Laser data performed poorly due to trace elements not directly contributing to Mg# calculation. 

- Dataset Suitability: Laser data is more effective for age classification, while EMPA data is more appropriate for predicting geochemical indices. 

Overall, the project demonstrates that model effectiveness depends strongly on the relationship between the dataset’s chemical signals and the prediction objective. Simpler models can outperform more complex ones when the data is well matched to the task.

