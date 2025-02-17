# Spaceship Titanic Kaggle Competition Solution

This Jupyter Notebook outlines a machine learning approach to the Spaceship Titanic Kaggle competition.  The goal is to predict whether passengers were transported to an alternate dimension.

## Data and Preprocessing

The notebook begins by downloading the competition dataset using the Kaggle API.  Extensive exploratory data analysis (EDA) is performed using the `ydata-profiling` library, generating a comprehensive report (`Spaceship_Titanic_Report.html`).  Preprocessing steps include:

* Handling missing values in `HomePlanet`, `CryoSleep`, `Destination`, `Age`, and `VIP` columns.
* Extracting `Deck` and `Side` information from the `Cabin` column.
* Filling missing values in monetary spending columns (`RoomService`, `FoodCourt`, etc.) with 0.
* Dropping the `Name` column due to high cardinality.
* One-hot encoding categorical features.

## Modeling

Several machine learning models are trained and evaluated:

* Random Forest
* Gradient Boosting
* Support Vector Machine (SVM)
* Logistic Regression

A `GridSearchCV` is used to optimize hyperparameters for each model using 10-fold cross-validation.  The models are trained on a train-test split (70/30) of the preprocessed data.

## Evaluation

Model performance is assessed using accuracy, precision, and recall on the test set.  The Gradient Boosting model demonstrates superior performance and is selected as the best model.

## Submission

The best model (`gradientBoosted.pkl`) is saved.  Predictions are made on the test dataset (`test.csv`), formatted into a submission file (`kaggle_submission.csv`), and submitted to the Kaggle competition.

## Kaggle API Setup

Before running the notebook, you need to:

1. Create a Kaggle account and download your `kaggle.json` API key.
2. Create a directory `~/.kaggle`.
3. Copy `kaggle.json` into `~/.kaggle/kaggle.json`.
4. Set the permissions: `chmod 600 ~/.kaggle/kaggle.json`

This will allow the notebook to automatically download the Spaceship Titanic dataset.


## Running the Notebook

Execute the Jupyter Notebook (`Spaceship_Titanic_Kaggle.ipynb`) to reproduce the analysis and model training.  Remember to have the Kaggle API set up correctly.
