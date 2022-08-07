# Neural_Network_Charity_Analysis
## Overview of the analysis
The purpose of this analysis was to use machine learning and neural networks in order to create a binary classifier which can predict whether applicants will be sucessful if they receive funding from Alphabet Soup.  The dataset utilized contained over 34,000 organizations which have received funding and whether the money they received was used effectively along with a variety of other features of the organizations and applications.

## Results
### Data Preprocessing
- The variable which was used as the target for the machine learning model was the "IS_SUCCESSFUL" column in the dataset, which determined whether the money an applicant received was used effectively.  This serves as a measure of whether or not the applicants were "successful" at utilizing the funding.
- The variables which were considered as features in the machine learning model were; 
  - "STATUS"
  - "ASK_AMT"
  - "APPLICATION_TYPE"
  - "AFFILIATION"
  - "CLASSIFICATION"
  - "USE_CASE"
  - "ORGANIZATION"
  - "INCOME_AMT"
  - "SPECIAL_CONSIDERATIONS".
  - All of these features other than "STATUS" and "ASK_AMT" were encoded using OneHotEncoder in order for the data to be used by the machine learning model.
- The variables from the original dataset which were neither targets nor features were the "EIN" and "NAME" columns which only served as identification columns.
### Compiling, Training, and Evaluating the Model
- In my initial model, I used the neuron and layer counts that were given in the starter code files, this was 2 hidden layers with 80 and 30 neurons respectively.  This seemed to be a fairly effective model, and since the dataset was so large with many columns and rows, it seemed that having a large number of neurons would be helpful for effective analysis.
- Overall, I was not able to achieve the target model performance of 75% but I was able to come fairly close.  With my initial model I achieved an accuracy of approximately 72.8%.  However, after performing some alterations to optimize the model I was able to achieve an accuracy of approximately 72.9%.
- The steps I took in order to attempt to increase the model performance were as follows;
  - I removed the "ASK_AMT" feature as it had many unique values meaning it could be causing unnessecary noise.
  - I added an additional hidden layer and additional neurons in each layer. However, this alone did not see any performance increase and rather saw a slight decrease in accuracy over the initial model.
  - I changed the activation method on the hidden layers for 'ReLu' to 'tanh'. This model had better accuracy than the one with additional neurons and hidden layers, but still slightly worse performance than the intial model.
  - Finally, I tried a combination of using the additional layer and neurons along with the change in activation method.  This model showed the best performance overall but it was only margianally better than the accuracy of the initial model.
  
## Summary
Overall, the machine learning model was only able to accuarately assess the success of potential applicants less than three quarters of the time.  Thus I do not think that this machine learning model would be able to effectively determine the success of a potential applicant.  Additionally, since the machine learning model is only attempting to classify the applicants as one of two potential outcomes, I think it could be equally effective and potentially more simple to use a Logistic Regression model in order to classify the applicants.  This would allow for a confusion matrix to be generated which might provide more clarity on the shortcomings of using machine learning in this situation.
