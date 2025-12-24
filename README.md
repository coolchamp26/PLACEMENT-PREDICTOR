# Student Placement Prediction

## Project Overview
This project demonstrates a simple machine learning workflow to predict student placement based on their academic performance (CGPA and IQ). A Logistic Regression model is trained, evaluated, and saved for future use.

## Data
The project uses a `Placement.csv` file, which is expected to contain the following columns:
- `Student_ID`: Unique identifier for each student.
- `CGPA`: Cumulative Grade Point Average.
- `IQ`: Intelligence Quotient score.
- `Placement`: A binary target variable (0 for not placed, 1 for placed).

## Dependencies
The following Python libraries are required to run this notebook:
- `numpy`
- `pandas`
- `matplotlib`
- `scikit-learn` (`sklearn`)
- `mlxtend`
- `pickle`

You can install these using pip:
```bash
pip install numpy pandas matplotlib scikit-learn mlxtend
```

## Usage
The notebook performs the following steps:
1.  **Load Data**: Reads the `Placement.csv` file into a pandas DataFrame.
2.  **Data Exploration**: Displays the head and info of the DataFrame, and visualizes the relationship between CGPA, IQ, and Placement using a scatter plot.
3.  **Prepare Data**: Separates features (X) and target (Y) variables. The features used are 'Student_ID' and 'CGPA', and the target is 'Placement'.
4.  **Split Data**: Divides the dataset into training (90%) and testing (10%) sets.
5.  **Feature Scaling**: Applies `StandardScaler` to scale the features in the training and testing sets.
6.  **Model Training**: Initializes and trains a `LogisticRegression` model on the scaled training data.
7.  **Model Evaluation**: Predicts placement on the test set and calculates the `accuracy_score`.
8.  **Visualize Decision Boundary**: Uses `mlxtend` to plot the decision regions of the trained classifier.
9.  **Save Model**: Saves the trained `LogisticRegression` model to a file named `model.pkl` using `pickle`.

## Saved Model
The trained Logistic Regression model is saved as `model.pkl`. This file can be loaded later to make predictions on new data without retraining the model.

```python
import pickle
loaded_model = pickle.load(open('model.pkl', 'rb'))
# Use loaded_model to make predictions
```
