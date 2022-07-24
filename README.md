# Lesson_14
# Primary application file

Produce a jupyter lab file that will combine algorithmic trading skills with existing skills in financial Python programming and machine learning to create an algorithmic trading bot that learns and adapts to new data and evolving markets.


---

## Technologies

The following Technologies were used to develop this program:

Python 
    Version 3.9.7

Terminal
    Version 2.12.5 (444)

Visual Studio Code
    Version: 1.66.2 (Universal)
    Commit: dfd34e8260c270da74b5c2d86d61aee4b6d56977
    Date: 2022-04-11T07:49:20.994Z
    Electron: 17.2.0
    Chromium: 98.0.4758.109
    Node.js: 16.13.0
    V8: 9.8.177.11-electron.0
    OS: Darwin x64 21.4.0
    
Jupyter Lab 
    Version 3.2.9
    


---

## General information about analysis.

Original SMA data:

Set the short window and long window:
short_window = 4
long_window = 100






Originial Training period of 3 months:

Select the start of the training period
training_begin = X.index.min()


Select the ending period for the training data with an offset of 3 months:
training_end = X.index.min() + DateOffset(months=3)

                precision    recall  f1-score   support

        -1.0       0.43      0.04      0.07      1804
         1.0       0.56      0.96      0.71      2288

    accuracy                           0.55      4092
   


![Originial SMA](/Original_SMA_plot.png)





Backtest original data with Logistic Regression:

                precision    recall  f1-score   support

        -1.0       0.44      0.33      0.38      1804
         1.0       0.56      0.66      0.61      2288

    accuracy                           0.52      4092
    
    
  ![Originial LR](/Original_withLR.png)








Updated SMA Data:

Select the start of the training period:
training_begin = X.index.min()


Select the ending period for the training data with an offset of 24 months:
training_end = X.index.min() + DateOffset(months=24)


Set the short window and long window
short_window = 25
long_window = 175

                precision    recall  f1-score   support

        -1.0       0.48      0.02      0.03      1155
         1.0       0.56      0.98      0.71      1458

    accuracy                           0.56      2613




![Updated SMA](/Updated_SMA_plot.png)








---

## Information about datasets

Data frame for OHLCV dataset:

ohlcv_df

Filter date index and pct_change function to generate returns from close prices:

signals_df

Assign a copy of the sma_fast and sma_slow columns:

X

Create target set for Signal column:

y

Set training beginning and ending dates, train data, and test data:

training_begin, training_end

X_train, y-train

X_test, y_test

Using StandardScaler fit and transform data:

scaler, X_scaler, X_train_scaled, X_test_scaled

Using SVC classifier model, fit, and predict data:

svm_model, svm_pred

Classification report from SVC model predictions:

svm_testing_report

Create a dataframe with predictions, actual returns, and strategy returns:

predictions_df

Logistic Regression model:

logistical_regression_model

Fit and predict model:

model, pred

Classification report:

test_pred

Create a dataframe with predictions, actual returns, and strategy returns for Logistic Regression model:

lr_predictions_df





---

## Libraries used in analysis

pandas

numpy

Path

hvplot

matplotlib

svm

StandardScaler

DateOffset

classification_report

LogisticRegression


---

## Contributors


**Chris Miskovich**

Contact Information:

Email: cmiskovich@verizon.net

[LinkedIn](https://www.linkedin.com/in/christopher-miskovich-9a61b0234/) 

---

## License

[MIT](/license.txt)
