# Mental Disorders Analysis

An exploratory data analysis and statistical hypothesis testing project examining
patterns in depression, anxiety, and Obsessive-Compulsive Disorder (OCD) across
three independent datasets.

---

## Overview

Mental health disorders affect millions of people worldwide, yet their underlying
patterns remain complex and multifaceted. This project investigates three of the
most prevalent conditions - **depression**, **anxiety**, and **OCD** - through
statistical analysis, hypothesis testing, and predictive modelling.

The analysis is structured in three parts:

1. **Exploratory Data Analysis (EDA)** - data cleaning, encoding, and visual exploration
2. **Hypothesis Testing** - non-parametric statistical tests with formal hypotheses
3. **Predictive Modelling** - Multiple Linear Regression for anxiety level prediction

---

## Datasets

| Dataset | Records | Source |
|---|---|---|
| Student Depression Dataset | ~27 000 | [Kaggle](https://www.kaggle.com/datasets/hopesb/student-depression-dataset) |
| Enhanced Anxiety Dataset | ~10 000 | [Kaggle](https://www.kaggle.com/datasets/natezhang123/social-anxiety-dataset/data) |
| OCD Patient Dataset | 1 500 | [Kaggle](https://www.kaggle.com/datasets/ohinhaque/ocd-patient-dataset-demographics-and-clinical-data) |

> **Note:** The Enhanced Anxiety Dataset and OCD Patient Dataset are synthetic.
> Results should not be interpreted as reflective of real-world clinical populations.

---

## Methods

### Statistical Tests

| Test | Purpose |
|---|---|
| **Chi-square** | Association between categorical variables and depression |
| **Shapiro-Wilk** | Normality check before choosing parametric vs. non-parametric tests |
| **Mann-Whitney U** | Comparing OCD symptom duration between two independent groups |
| **Kruskal-Wallis H** | Comparing Y-BOCS scores across obsession and compulsion types |

### Predictive Model

**Multiple Linear Regression** trained to predict `anxiety_level_1_10` from
lifestyle, physiological, and psychological features using:

- `StandardScaler` for feature normalization
- 5-Fold Cross-Validation for reliable performance estimation
- Standardized coefficients for feature importance interpretation

**Results:** $ R^2 $ = 0.729, MSE = 1.255 (RMSE $ \approx $ 1.12 on a 1-10 scale)

---

## Key Findings

- **Family history of mental illness** is statistically associated with depression
  in students ($ \chi^2 $ test, p $ \approx $ 7.5 $ \times $ $ 10^{-19} $)
- **Gender** is not significantly associated with depression (p = 0.74)
- **Comorbid depression and anxiety** do not significantly alter OCD symptom
  duration compared to patients with neither condition (Mann-Whitney U, p = 0.103)
- **Y-BOCS scores** do not differ significantly across obsession types (H = 4.769,
  p = 0.312) or compulsion types (H = 9.383, p = 0.052)
- **Stress level** is the strongest predictor of anxiety (standardized $ \beta $ $ \approx $ 1.10),
  followed by therapy sessions per month and sleep hours

---

## Project Structure

```
mental-disorders-analysis/
|-- disorders-analysis/
|   |-- data/
|   |   |-- Student Depression Dataset.csv
|   |   |-- enhanced_anxiety_dataset.csv
|   |   |-- ocd_patient_dataset.csv
|   |-- disorders-analysis.ipynb
|-- .gitignore
|-- LICENSE
|-- README.md
```

---

## Requirements

```
pandas
numpy
scipy
scikit-learn
matplotlib
seaborn
```

Install all dependencies with:

```bash
pip install pandas numpy scipy scikit-learn matplotlib seaborn
```

---

## How to Run

1. Clone the repository:

```bash
git clone https://github.com/VladoDev03/mental-disorders-analysis.git
cd mental-disorders-analysis
```

2. Install dependencies:

```bash
pip install pandas numpy scipy scikit-learn matplotlib seaborn
```

3. Launch Jupyter:

```bash
cd disorders-analysis
jupyter notebook disorders-analysis.ipynb
```

4. Run all cells: **Kernel $ \rightarrow $ Restart & Run All**

---

## References

### Datasets
- [Student Depression Dataset](https://www.kaggle.com/datasets/hopesb/student-depression-dataset)
- [Enhanced Anxiety Dataset](https://www.kaggle.com/datasets/natezhang123/social-anxiety-dataset/data)
- [OCD Patient Dataset](https://www.kaggle.com/datasets/ohinhaque/ocd-patient-dataset-demographics-and-clinical-data)

### Academic
- [Yale-Brown Obsessive Compulsive Scale](https://pubmed.ncbi.nlm.nih.gov/2684084)

### Statistical Methods
- [Kruskal-Wallis Test](https://www.datacamp.com/tutorial/kruskal-wallis-test?utm_source=copilot.com)
- [Shapiro-Wilk Normality Test](https://scienceinsights.org/how-to-interpret-the-shapiro-wilk-normality-test)
- [Mann-Whitney Test](https://scienceinsights.org/what-is-a-mann-whitney-test-and-how-does-it-work)
- [Kolmogorov-Smirnov Test](https://www.socscistatistics.com/tutorials/kolmogorov-smirnov)
- [Multiple Linear Regression](https://en.wikipedia.org/wiki/Linear_regression)
