# Advertising Sales Prediction

Linear regression on the Kaggle Advertising dataset — predicting product sales
from TV, Radio and Newspaper ad budgets.

## Dataset

[Advertising Dataset](https://www.kaggle.com/datasets/ashydv/advertising-dataset) — 200 rows, 4 columns (TV, Radio, Newspaper, Sales). No missing values, all continuous.

## What's in here

- `notebooks/advertising.ipynb` — EDA, preprocessing, model training and evaluation.

## Approach

1. Explored distributions and feature-target relationships. TV shows a strong
   positive relationship with Sales; Radio is weaker; Newspaper is close to flat.
2. Split 80/20, standardized features using training statistics only.
3. Compared Linear, Ridge and Lasso regression.

## Results

| Model  | MAE   | RMSE  | R²     |
|--------|-------|-------|--------|
| Linear | 1.275 | 1.705 | 0.906  |
| Ridge  | 1.273 | 1.707 | 0.906  |
| Lasso  | 1.789 | 2.344 | 0.822  |

Linear and Ridge are basically tied. Lasso underperforms at the default
`alpha=1.0`, which I haven't tuned yet — that's next.

## Setup

```bash
pip install -r requirements.txt
jupyter notebook notebooks/advertising.ipynb