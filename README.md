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

# Set the short window and long window
short_window = 4
long_window = 100

# Generate the fast and slow simple moving averages (4 and 100 days, respectively)
signals_df['SMA_Fast'] = signals_df['close'].rolling(window=short_window).mean()
signals_df['SMA_Slow'] = signals_df['close'].rolling(window=long_window).mean()

signals_df = signals_df.dropna()

# Review the DataFrame
display(signals_df.head())
display(signals_df.tail())

Originial Training period of 3 months:

# Select the start of the training period
training_begin = X.index.min()

# Display the training begin date
print(training_begin)


# Select the ending period for the training data with an offset of 3 months
training_end = X.index.min() + DateOffset(months=3)

# Display the training end date
print(training_end)











The Lesson consists of three technical deliverables:

Preprocess data for a nerual network model.

Use the model-fit-predict patten to complile and evaluate a binary classification model.

Optimize the model.



First you have to prepare the data for a nerual network model.  You create a data frame using the applicant data csv file.  Then drop EIN and NAME columns from the file since they are not needed for the model.  You then encode the data set's variables using one hot encoder.  After that numerical_variables_df and encoded_df data frames are concatenated to add numberical variables from original data frame to match the one hot encoded data frame.  You then prepare the X and y data frames and run a train_test_split function.  You will then need to scale the data.  Now we are ready to compile and evaluate a binary classification using a neural network.

The first neural network "Original Model Results" used all of the input features and the first hidden layer of 25 nodes and a second hidden layer of 12 nodes and used the "relu" activation.  We then compiled the model using binary crossentropy as the loss, optimizer equal to adam, and metrics equal to accuracy and fit the model using 50 epochs.  The results were 61.25% loss and 73.01% accuracy.  We then created an HDF5 file called AlphabetSoup.hd and saved it in our Resources directory.

The next step was to run an Alternative Model 1 and in this model we used all inputs for number of input features then used only one hidden layer of 58.  The hidden layer we used "relu" as activation and "sigmoid" activation in the output layer.  The results improved, loss decreased to 55.64% and accuracy increased to 73.15%.

Alternative Model 2 I was hoping to increase accuracy by adding more nodes to hidden layer 1 along with adding two addtional hidden layers from Alternative Model 1.  Using "relu" on the three hidden layers and "sigmoid" on the output layer.  Also wanted to increase accuracy by running additional epochs increasing the amount from Alternative Model 1 at 50 to 110 for Alternative Model 2.  Loss was worse slightly going from 55.64% in Alternative Model 1 to 59.27% in Alternative Model 2.  However, accuracy slightly increased from 73.15% in Alternative Model 1 to 73.17% in Alternative Model 2.  

After comparing the two alternative models you then create a HDF5 file and save them to Resources directory for Alternative Model 1 (AlphabetSoup_A1.hd) and for Alternative Model 2 (AlphabetSoup_A2.hd).



---

## Information about datasets

Data frame applicants to be used on a neural network model:

applicant_data_df

List of categorical variables:

categorical_variables

Data sets for OneHotEncoder:

enc

encoded_data

Add numerical variables from original data frame to the one hot encoding dataframe:

numerical_variables_df

attition_df

Create the X and y datasets:

X, y

Split the dat using train test spilt function:

X_train, X_test, y_train, y_test = train_test_split(X, y, random_state=1)

Scale the X data:

scaler

X_scaler

X_train_scaled

X_test_scaled

Create a deep neural network:

Original dataset using 2 hidden layers:

number_input_features

number_output_neurons

hidden_nodes_layer1

hidden_nodes_layer2

Alternative Model 1 using 1 hidden layer:

number_input_features

number_output_neurons_A1

hidden_nodes_layer1_A1

Alternative Model 2 using 3 hidden layers:

number_input_features

number_output_neurons_A2

hidden_nodes_layer1_A2

hidden_nodes_layer2_A2

hidden_nodes_layer3_A2

Create, compile, fit, and evaluate models for neural network:

nn, nn_A1, nn_A2

model, fit_model_A1, fit_model_A2

model_loss, model_accuracy

Create HDF5 files for each dataset:

AlphabetSoup.h5

AlphabetSoup_A1.h5

AlphabetSoup_A2.h5




---

## Libraries used in analysis

pandas

Path

tensorflow

tensorflow.keras.layers, Dense

tensorflow.keras.models, Sequential

train_test_split

StandardScaler

OneHotEncoder

---

## Contributors


**Chris Miskovich**

Contact Information:

Email: cmiskovich@verizon.net

[LinkedIn](https://www.linkedin.com/in/christopher-miskovich-9a61b0234/) 

---

## License

[MIT](/license.txt)
