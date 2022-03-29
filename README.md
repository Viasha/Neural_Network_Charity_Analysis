# Neural_Network_Charity_Analysis
## Oveview
The purpose of the project was to express my knowledge of machine learning and neural networks. I will use the features in the dataset provided by Alphabet Soup's business team to help Beks create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.
Alphabet Soup would like to determine which organizations would be worth donating to and which ones are considered "high-risk". I used Deep Learning Neural Networks to evaluate the input data and produce clear results.

## Results
The CSV provided by Alphabet Soup contained more than 34,000 organizations. Within this dataset are a number of columns that capture metadata about each organization, such as the following:

EIN and NAME—Identification columns

APPLICATION_TYPE—Alphabet Soup application type

AFFILIATION—Affiliated sector of industry

CLASSIFICATION—Government organization classification

USE_CASE—Use case for funding

ORGANIZATION—Organization type

STATUS—Active status

INCOME_AMT—Income classification

SPECIAL_CONSIDERATIONS—Special consideration for application

ASK_AMT—Funding amount requested

IS_SUCCESSFUL—Was the money used effectively

### Data Preprocessing
In order to have the appropriate data for the model I have to preprocess the data in order to compile, train and evaluate the neural network model. 
* I removed the columns EIN and NAME because they hold no significance to the model.
* I created a bin for the APPLICATION_TYPE column to categorize types less than 500 as "Other".
* I used the IS_SUCCESSFUL column as my target variable.

### Compiling, Training and Evaluating the Model
Now that the data is preprocessed, I can compile, train and evaulate the model with these steps:
* I chose 80 neurons for the first hidden layer with a ReLu function, 30 neurons for the second hidden layer also witha  ReLu function. For the output layer I chose a sigmoid function. 
* The target market performance was 72.16% accuracy rate and 55.95% loss . The model was unfortunately unable to reach 75% accuracy. 

![Original_results](https://user-images.githubusercontent.com/93167609/160541507-d478e2f0-f688-45fb-800f-19408f4c1256.png)

* To optimize the model I changed features, neuron amounts and epochs. 
  * On my first attempt I binned the INCOME_AMT column to adjust the features. This did not affect my accuracy much. The new accuracy rate was 72.54%. The Loss was 57.08%. These results were slightly better than the previous optimization.

![feature_optimization](https://user-images.githubusercontent.com/93167609/160542509-c7ab72c2-96a7-4a45-a887-d4d910c36318.png)

  * For this optimization I removed the ORGANIZATION column and kept the INCOME_AMT column binned. I removed the SPECIAL_CONSIDERATIONS_Y column as a feature because the SPECIAL_CONSIDERATIONS_N column is sufficient. I also increased the amount of neurons to 100 for the first hidden layer and 50 for the second hidden layer. The 
accuracy rate for this adjustment was 72.37% and the loss was 59.27%. This was a slight increase from the previous optimization. 

![features_neuron_optimization](https://user-images.githubusercontent.com/93167609/160546617-f16fa953-f7e2-408e-8fab-1e3f751bc320.png)

* In my final attempt to optimize the model, I binned both INCOME_AMT and AFFILIATION columns. As described in the previous optimization, I removed the SPECIAL_CONSIDERATIONS_Y column. I increased the amount of neurons to 125 for the first hidden layer, and 50 for the second. This affected the accuracy rate of the model to 72.60% and a loss of 60.24%. These adjustments slightly increased the results but nothing of significance. 

## Summary
The Deep Learning Model I created unfortunately did not reach our desired accuracy rate of 75%. With various optimizations, I achieved a high accuracy rate of 72.60% when I adjusted the features and neurons. The changes made did not significantly effect the results yielded from the neural network model. I would suggest attempting a Random Forest Classifier model which would build simplier decision trees. 
