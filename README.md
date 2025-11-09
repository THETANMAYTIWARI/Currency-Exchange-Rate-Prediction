## 💱 Currency Exchange Rate Prediction using Support Vector Machine (SVM)

This project aims to predict future currency exchange rates using Support Vector Regression (SVR) — a powerful machine learning model capable of handling nonlinear financial data trends.
It includes an interactive Tkinter-based GUI that allows users to visualize and forecast exchange rate movements over different time periods.

### 📘 Project Overview

The project leverages a historical Forex dataset and applies data preprocessing, feature transformation, and Support Vector Regression (SVR) to build an accurate predictive model for currency exchange rates.
Users can interact with a simple graphical interface to visualize predictions for 1-month, 3-month, and 6-month durations.

### 🧠 Key Features

#### 📊 Data Analysis & Visualization

* Exploratory Data Analysis (EDA) with correlation heatmaps, variation, and log-variation plots.

* Country-specific and currency-based trend visualizations.

#### ⚙️ Machine Learning Model

* Implemented using Support Vector Regression (SVR) with an RBF kernel.

* Includes data scaling using StandardScaler.

* Model persistence with pickle for reuse without retraining.

#### 🪟 Interactive User Interface

* Built using Tkinter.

* Allows selection of prediction duration (1, 3, or 6 months).

* Displays forecasted trends using Matplotlib and OpenCV.

### 🚀 How to Use
#### 🧰 Prerequisites

Ensure you have the following libraries installed:
```
pip install numpy pandas matplotlib seaborn scikit-learn opencv-python pillow tkinter
```
#### 📈 To Train or Recreate the Model

1.) Open the 20MIA1097_ML_PROJECT.ipynb file.

2.) Change the value of slug11 to your desired currency pair (e.g., "USD/INR").

3.) Run all cells below the comment # SVM STARTS FROM HERE.

4.) The model will be trained and saved as finalized_model.sav.

#### 💻 To Run the User Interface

1.) Open 20MIA1097_ML_PRO.py in your IDE or terminal.

2.) Update the path to your model file:
```
filename = 'path/to/finalized_model.sav'
```
3.) Run the script:
```
python 20MIA1097_ML_PRO.py
```
4.) Use the GUI to:

* Enter Currency 1 and Currency 2

* Choose Time Period (1, 3, or 6 months)

* Click Predict to visualize the forecasted rate trend.
