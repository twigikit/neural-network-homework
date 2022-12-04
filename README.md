# Neural Network Model

The Alphabet Soup business has requested a model to predict whether the startup requesting for funding will become successful if funded by Alphabet Soup. To assist with the modelling, Alphabet Soup has provided various typs of information about more than 34000 organisation that they have provided funding over the years, including whether they ultimately became successful or not. 

This exercise involves creating a binary classificary model, whether the applicant will be successful or not, using a deep neural network. 

The following steps are taken:
1. Prepare data - Applicant information was provided in a CSV file. Read CSV file into a pandas dataframe, review data and check for categorical variables that will need to be encoded and for columns that might eventually define as features and target variables. 
* Applicant identifiers such as Employer Identification Number and Name were removed.
* Categorical variables are encoded using OneHotEncoder (an alternative to pandas get_dummies function).
* Numerical variables of the original datafrme was added to the dataframe that contains the encoded variables. 

2. Preprocess data - The "IS_SUCCESSFUL" column set as the target. The remaining columns are defined as the features dataset. Data is then split into two sets: training set and testing set.  StandardScaler from scikit-learn is used to scale the feature data.

3. Design the model - Use TensorFlow to design a binary classification deep neural network model. 
* Model 1 is a two-layer deep neural network model that uses "relu" activation function for both layers. Model 1 is then compiled using the binary_crossentropy loss function, the "adam" optimiser and the "accuracy" evaluation metric. Model 1 is then fit using 50 epochs.

4. Optimise the model
* Attempt 1 - Add more hidden layers and reduce the number of epochs in the training regime
* Attempt 2 - Use different activation functions for the hidden layers and reduce the number of epochs in the training regime

5. Evaluate the model using the loss and accuracy metrics

