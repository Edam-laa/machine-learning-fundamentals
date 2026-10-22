# Machine Learning Fundamentals

**Applied ML notebooks · Regression · Classification · Clustering · Introductory Neural Networks**

A curated collection of academic exercises and independent learning notebooks. This is a learning portfolio, not a production ML service or a benchmark suite. The aim is to make the problems, methods, source notebooks and reproducibility limitations easy to inspect.

## Notebook index

| Topic | Notebook | Focus |
| --- | --- | --- |
| Regression | [Ames Housing linear regression](regression/linear_regression_ames_housing.ipynb) | Linear models and residential price data |
| Regression | [Housing price prediction](regression/house_price_prediction.ipynb) | Supervised numerical prediction |
| Regression | [Car price KNN](regression/car_price_prediction_knn.ipynb) | Nearest-neighbor regression |
| Classification | [Admissions logistic regression](classification/logistic_regression_admissions.ipynb) | Binary classification |
| Classification | [Automobile multiclass](classification/multiclass_classification_auto.ipynb) | Multiclass labels |
| Classification | [Bias, variance and overfitting](classification/overfitting_bias_variance.ipynb) | Generalization |
| Clustering | [Congress voting K-Means](clustering/kmeans_congress_votes.ipynb) | Cluster exploration |
| Clustering | [NBA K-Means](clustering/kmeans_nba_players.ipynb) | Grouping player statistics |
| Neural Networks | [Iris neural network](neural_networks/simple_neural_network_iris.ipynb) | Introductory classification |
| Finance | [Stock-market prediction](stock_market_prediction/stock_market_prediction.ipynb) | Exploratory forecasting |

Each notebook has its own analytical question and inputs. Scores from unrelated datasets and splits should not be compared as if they constituted a single benchmark.

## Repository layout

```text
classification/             # Logistic, multiclass and overfitting examples
clustering/                 # K-Means exercises
neural_networks/            # Iris example
regression/                 # House/car price exercises
stock_market_prediction/    # Financial series exploration
requirements.txt            # Python notebook libraries
```

## Run locally

```bash
git clone https://github.com/Edam-laa/machine-learning-fundamentals.git
cd machine-learning-fundamentals
python -m venv .venv
# Activate your environment:
# Windows PowerShell: .venv\Scripts\Activate.ps1
# Linux/macOS: source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter notebook
```

Select a notebook from the index and execute its cells sequentially. Associated datasets are typically in each topic's `data/` directory. Some notebooks may still contain local filesystem paths or environment-dependent assumptions: adjust these cautiously rather than treating the repository as fully reproducible.

## Reviewing ML quality

Meaningful questions for every notebook are: what dataset and prediction target were used, what baseline was considered, how train/test data were separated, how missing values were handled, which metrics were chosen, and whether the model might leak test information. Improvements should focus on these concerns before adding decorative badges.

**Validation status:** This README update does not include a fresh run of every notebook. No accuracy, RMSE, test-pass or coverage figure is claimed without reproducible evidence.

## Why no pipeline diagram?

This repository is a **collection of independent notebooks**, not a shared end-to-end application. A clear index is a more truthful and useful portfolio presentation than inventing a pipeline.

## Next improvements

- Add a compact learning-objective, dataset, evaluation and limitations section to individual notebooks.
- Normalize source paths and random seeds.
- Run a selected subset in a clean environment and record outcomes.
- Add baseline comparisons and proper train-only preprocessing where appropriate.
- Keep financial forecasting claims explicitly exploratory.

## Context

Educational material that supports further AI engineering and data science projects.
