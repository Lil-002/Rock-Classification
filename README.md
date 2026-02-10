# Age Classification and Geochemical Prediction of Volcanic Rocks

## Project Overview

This project investigates whether geochemical data can be used to accurately determine the **age classification** of volcanic rock samples and to predict their **geochemical maturity (Mg#)**. Two analytical datasets—**Electron Microprobe Analysis (EMPA)** and **Laser Ablation**—are compared to evaluate which is more suitable for each predictive task.

The work demonstrates how dataset characteristics directly influence model performance and shows that well-matched, simpler models can outperform more complex approaches.

---

## Objectives

* Classify volcanic rock samples into **three age groups**.
* Predict **Mg#** as a measure of rock maturity.
* Compare the effectiveness of **EMPA vs Laser** datasets.
* Evaluate multiple machine learning models for both classification and regression tasks.

---

## Key Questions

* Which dataset better separates volcanic rock age groups?
* Which dataset better predicts geochemical indices?
* Do complex models outperform simpler statistical approaches?

---

## Dataset Description

Two geochemical datasets with different structures were used:

### EMPA Dataset

* Major element chemistry.
* Mostly complete data.
* Best suited for deriving geochemical ratios such as Mg#.

### Laser Ablation Dataset

* Trace element concentrations.
* Approximately **71% missing values**.
* Strong compositional variation across age groups.

### Data Processing

* Non-numeric values converted to NaN.
* Values below detection limits handled using **LOD/2**.
* Fully empty rows removed (Laser dataset).
* Median imputation applied.
* Train–test split performed before scaling and imputation to prevent data leakage.

---

## Methodology

### Workflow

1. Data Cleaning and Exploration
2. Feature Preparation
3. Model Training and Evaluation

### Classification Models

* Logistic Regression (Baseline)
* Random Forest
* Neural Network (TensorFlow/Keras)

**Metric:** F1 Score

### Regression Model

* Linear Regression

**Metric:** R² Score

---

## Exploratory Data Analysis Insights

### EMPA

* Element concentrations remain largely stable across age groups.
* Significant overlap between categories.
* Limited ability to distinguish ages visually.

### Laser

* Clear compositional trends across age groups.
* V-shaped and inverted V-shaped element patterns (e.g., Cr, Ni, Zr, Sr).
* Stronger predictive signals for classification.

---

## Results

### Classification Performance

| Model               | Best Outcome                              |
| ------------------- | ----------------------------------------- |
| Logistic Regression | Highest overall F1 Score (~0.97)          |
| Neural Network      | Better performance on individual datasets |
| Random Forest       | Competitive but not consistently superior |

### Regression Performance

| Dataset | R² Score                                                     |
| ------- | ------------------------------------------------------------ |
| EMPA    | ~0.995 (near perfect prediction of Mg#)                      |
| Laser   | Poor performance (trace elements not directly linked to Mg#) |

---

## Key Findings

* **Laser data** is more effective for **age classification**.
* **EMPA data** is more suitable for **geochemical prediction**.
* Dataset–model alignment is more important than model complexity.
* Logistic Regression proved to be the most reliable overall classifier.

---

## Repository Structure

```
Age-Classification-Volcanic-Rocks/
│
├── README.md
│
├── data/
│   └── Ali_New_Spreadsheet.xlsx
│
├── notebooks/
│   ├── 01_Data_Cleaning_and_EDA.ipynb
│   ├── 02_Data_Preparation.ipynb
│   └── 03_Model_Training_and_Evaluation.ipynb
│
├── reports/
│   ├── Summary_Report.pdf
│   └── Data_Visualization_Report.pdf
│
└── requirements.txt
```

---

## Technologies Used

**Environment**

* Google Colab

**Language**

* Python

**Libraries**

* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* TensorFlow / Keras

---

## How to Run the Project (Google Colab)

1. Open the repository.
2. Navigate to the **notebooks** directory.
3. Open each notebook using Google Colab.
4. Mount Google Drive:

```python
from google.colab import drive
drive.mount('/content/drive')
```

5. Ensure the dataset file is placed in the referenced `/data` directory or Google Drive path.
6. Execute notebooks in sequence:

* `01_Data_Cleaning_and_EDA`
* `02_Data_Preparation`
* `03_Model_Training_and_Evaluation`

All visualisations, processed datasets, and model results will be generated automatically.

---

## Limitations

* High missing data in the Laser dataset required careful preprocessing.
* Neural network reproducibility required fixed random seeds.

---

## Future Improvements

* Apply feature engineering and dimensionality reduction techniques.
* Test ensemble and gradient boosting approaches.
* Increase dataset size for improved generalisation.

---

## Author

[Your Name]
AI / Data Science Portfolio Project


