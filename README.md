# Machine Learning Fundamentals — Applied Learning Portfolio

**Python · NumPy · Pandas · scikit-learn · Exploratory Analysis · Supervised & Unsupervised Learning**

A collection of **10 academic and self-study Jupyter notebooks** covering regression, classification, clustering, generalization, neural-network fundamentals and a first time-series experiment.

This is a **learning laboratory**, not a single production application or a leaderboard. Each notebook explores a separate dataset or algorithm; the value is in the implementation choices, statistical reasoning and lessons learned.

> **Evidence standard:** all notebooks linked below exist in the repository. Some are older exercises with missing source files, local-path assumptions or evaluation weaknesses. No aggregate accuracy, RMSE, cross-validation score or reproducibility guarantee is invented here.

## Start here — four representative notebooks

| Recommended entry point | Technical focus | What to inspect |
| --- | --- | --- |
| **[Housing prices: preprocessing and model selection](regression/house_price_prediction.ipynb)** | Linear regression, feature engineering, missingness, encoding, RMSE and cross-validation exercises | How preprocessing and the evaluation protocol affect regression estimates |
| **[Car prices: K-nearest neighbors](regression/car_price_prediction_knn.ipynb)** | Numerical data cleaning, normalization, KNN regression and neighbor/feature comparisons | Why distance-based models require careful scaling and choice of `k` |
| **[NBA player clustering](clustering/kmeans_nba_players.ipynb)** | Hand-built K-Means steps, centroid assignment/updates and scikit-learn comparison | How iterative unsupervised grouping works beneath a library API |
| **[Neural network from numerical building blocks](neural_networks/simple_neural_network_iris.ipynb)** | Sigmoid, feedforward, cost functions, gradient descent and a hand-written network class | Core training mechanics without treating a library call as an explanation |

**Suggested review order:** KNN regression → housing-model experiments → manual K-Means → neural-network internals. These examples offer more technical depth than browsing ten unrelated notebooks at random.

## Complete notebook directory

| Area | Notebook | Dataset / objective | Key methods |
| --- | --- | --- | --- |
| Regression | [Ames Housing: linear regression](regression/linear_regression_ames_housing.ipynb) | Predict housing sale price | Exploratory correlations, linear models, train/test RMSE |
| Regression | [Ames Housing: extended workflow](regression/house_price_prediction.ipynb) | Compare feature/preprocessing choices | Missing values, encoding, feature selection, regression and fold experiments |
| Regression | [Automobile price prediction with KNN](regression/car_price_prediction_knn.ipynb) | Estimate car prices | Nearest-neighbor regression, scaling, `k` and feature comparisons |
| Classification | [Admissions: logistic regression](classification/logistic_regression_admissions.ipynb) | Explore admission probability | Sigmoid and logistic classification — **input CSV missing** |
| Classification | [Automobile origin classification](classification/multiclass_classification_auto.ipynb) | Predict car origin categories | Logistic one-vs-rest-style probability comparison |
| Generalization | [Bias, variance and overfitting](classification/overfitting_bias_variance.ipynb) | Study model complexity and MPG error | Linear regression, feature-set comparisons, 10-fold CV |
| Clustering | [Congress votes: K-Means](clustering/kmeans_congress_votes.ipynb) | Explore voting-record similarity | Euclidean distances, clustering and descriptive comparisons |
| Clustering | [NBA point guards: K-Means](clustering/kmeans_nba_players.ipynb) | Group players by performance indicators | Manual centroids, assignment and scikit-learn K-Means |
| Neural networks | [Iris: neural-network fundamentals](neural_networks/simple_neural_network_iris.ipynb) | Understand binary classification on Iris | Sigmoid, loss, feedforward, backpropagation and a custom class |
| Time series | [Stock-market price experiment](stock_market_prediction/stock_market_prediction.ipynb) | Model historical index closing prices | Lagged rolling feature, calendar variables, chronological split, linear regression |

No claim is made that results from separate datasets are directly comparable. In particular, the financial notebook is an **introductory historical exercise**, not a trading system or validated forecasting strategy.

## How to navigate the learning material

```text
regression/
  data/                           Ames Housing and automobile datasets
  linear_regression_ames_housing.ipynb
  house_price_prediction.ipynb
  car_price_prediction_knn.ipynb

classification/
  data/                           Automobile datasets (admissions CSV absent)
  logistic_regression_admissions.ipynb
  multiclass_classification_auto.ipynb
  overfitting_bias_variance.ipynb

clustering/
  data/                           Congress voting and NBA 2013 datasets
  kmeans_congress_votes.ipynb
  kmeans_nba_players.ipynb

neural_networks/
  data/                           Iris dataset
  simple_neural_network_iris.ipynb

stock_market_prediction/
  data/                           Historical market CSV
  stock_market_prediction.ipynb

requirements.txt                  Common notebook dependencies
```

## What the experiments teach

### Supervised learning — choosing a meaningful baseline

The housing and automobile regression notebooks explore the difference between fitting a model and **evaluating it on unseen observations**. They use interpretable baselines such as linear regression and KNN regression, with RMSE as a measure of price-estimation error.

**Key lesson:** comparing features or hyperparameters on a fixed test set can bias conclusions. Preprocessing and feature selection should be fitted **inside the training split or cross-validation folds**, rather than on all observations before evaluation.

### Classification — probabilities and decision boundaries

The logistic-regression exercises introduce binary probabilities and multiclass category selection. These are foundations, not a complete classification benchmark: robust comparison would also require class-aware splitting, confusion matrices, precision/recall and a declared target metric.

### Unsupervised learning — learn the mechanics

The NBA notebook implements important K-Means operations explicitly before using scikit-learn. The Congress notebook explores similarity structure in voting data. Both are **descriptive grouping experiments**; clusters must not automatically be interpreted as objective categories or causal explanations.

### Neural networks — beyond a black-box API

The Iris notebook walks through sigmoid activations, loss computations and learning steps using numerical code and a hand-written network class. It is a conceptual implementation exercise, **not a PyTorch/TensorFlow production model**. Training correctness, shapes and evaluation still require a clean-run review.

### Time series — chronology matters

The market notebook uses a lagged rolling average and a time-based train/test boundary. This introduces an essential forecasting principle: historical signals must be constructed without information from the future. Its missing-value handling and evaluation assumptions need review before the recorded experiment can be considered reliable.

## Run locally

**Requirements:** Python, pip and Jupyter.

```bash
git clone https://github.com/Edam-laa/machine-learning-fundamentals.git
cd machine-learning-fundamentals
python -m venv .venv
# Activate the environment for your OS
python -m pip install -r requirements.txt
jupyter notebook
```

Open an individual notebook **from its topic directory** and execute its cells in order. Most supplied datasets reside in that topic's `data/` folder. Some code still depends on current working directory, historical library behavior or a local file that is not committed.

**Known first-run blocker:** `classification/logistic_regression_admissions.ipynb` refers to `classification/data/admissions.csv`, which is **not in the repository**. That notebook cannot be reproduced without obtaining an authorized copy of the original data or updating the exercise to use a replacement dataset.

**Additional cautions:** the Iris neural-network notebook includes exploratory code that has not been clean-run verified; the housing workflow performs some feature preparation and selection before evaluation; the market notebook contains a `dropna()` call without assigning the returned frame. These are technical debt, not hidden successful tests.

## Portfolio quality and validation status

What the repository **does demonstrate**:

- Direct implementation of core ML methods across several small datasets.
- Practical experience with Pandas, scikit-learn, visualization and numerical operations.
- Exposure to model evaluation, cross-validation and feature-engineering trade-offs.
- Exploration of algorithm internals, including manual K-Means and neural-network calculations.

What it **does not yet demonstrate**:

- A unified, automatically tested or deployable ML pipeline.
- A shared, versioned benchmark with reproducible model metrics.
- Verified zero-leakage training/evaluation across every notebook.
- Automated tests, continuous integration or complete dependency locking.
- Model monitoring, inference API endpoints or production deployment.

## Improvement roadmap

1. **Reproducibility:** repair missing inputs and working-directory assumptions; execute every notebook in a fresh environment.
2. **Evaluation:** use explicit baselines, deterministic splits, train-only transforms, task-appropriate metrics and held-out validation.
3. **Documentation:** add a short *Problem → Dataset → Method → Results → Limitations* summary within each notebook.
4. **Evidence:** preserve reproducible plots and a compact results table **only after** clean execution.
5. **Progression:** graduate the most complete exercises into independent end-to-end ML projects instead of presenting this collection as one large application.

## Project context

Educational ML work supporting later projects in **Data Science, Document AI, RAG and AI Engineering**. For recruiters, this repository is best read as **evidence of foundations and learning progression**, while larger end-to-end projects should demonstrate architecture, evaluation and delivery.
