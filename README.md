# Neural Network Model

The Alphabet Soup business has requested a model to predict whether the startup requesting for funding will become successful if funded by Alphabet Soup. To assist with the modelling, Alphabet Soup has provided various typs of information about more than 34000 organisation that they have provided funding over the years, including whether they ultimately became successful or not. 

This exercise involves creating a binary classificary model using a deep neural network that output the indicator whether the applicant will be successful or not.

The following steps are taken:
1. **Prepare data** - Applicant information was provided in a CSV file. Read CSV file into a pandas dataframe, review data and check for categorical variables that will need to be encoded and for columns that might eventually define as features and target variables. 
* Applicant identifiers such as Employer Identification Number and Name were removed.
* Categorical variables are encoded using OneHotEncoder (an alternative to pandas get_dummies function).
* Numerical variables of the original datafrme was added to the dataframe that contains the encoded variables. 

2. **Preprocess data** - The "IS_SUCCESSFUL" column set as the target. The remaining columns are defined as the features dataset. Data is then split into two sets: training set and testing set.  StandardScaler from scikit-learn is used to scale the feature data.

3. **Design the model** - Use TensorFlow to design a binary classification deep neural network model. <br>
**Model 1** is a two-layer deep neural network model that uses "relu" activation function for both layers. Model 1 is then compiled using the binary_crossentropy loss function, the "adam" optimiser and the "accuracy" evaluation metric. Model 1 is then fit using 50 epochs.

4. **Optimise the model**
* Attempt 1 (Alternative Model 1) - Add more hidden layers and reduce the number of epochs in the training regime. Use the same parameter values as model 1 for compilation. 

* Attempt 2 (Alternative Model 2) - Use different activation functions for the hidden layers and reduce the number of epochs in the training regime. Use the same parameter values as model 1 for compilation. 

5.**Evaluate the models** using the loss and accuracy metrics

### Results
|  | Loss Score | Accuracy Score |
|--|------------|----------------|
|Model 1| 0.5507 | 0.7300 |
|Alternative Model 1 | 0.5531 | 0.7329 |
|Alternative Model 2 | 0.5509 | 0.7310 |

The original model (Model 1) has an accurarcy score of 0.7300 and loss score of 0.5507. As we increase the number of hidden layers (Alternative Model 1), the accuray is slightly improved but no changes to losses. A different activation function (i.e. tanh instead of relu) does improve the accuracy slightly. 

### Conclusion
There is further opportunity to prune the model.  We recommend future pruning consider adjusting the input data by dropping different features combination or a combination of add more hidden layers and different activation functions.