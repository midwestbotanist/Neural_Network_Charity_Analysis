# Alphabet Soup: Analysis of Organizations Funded

## Background and Purpose:
Alphabet Soup is a company with philanthropy as its core value. It seeks to help organizations that focus on protecting the environment, improving well being, and unifying the world. Over two decades, Alphabet Soup has invested a combined $10 billion into life saving technologies and improving deforestation around the world. The purpose for this analysis is to see how the funding has impacted the organizations and further vet the recipients. This is a necessary analysis in order to ensure that the organization's money is effective. The company is aware of cases in which companies disappeared following reception of the funds. Due to this, the company wishes to create a prediction algorithm to better determine which companies are worth giving donations vs those that are too risky. 

Due to the complexity of the analysis being done, traditional analysis/machine learning have been set aside in favor of a deep learning neural network. It will evaluate all of the data collected by Alphabet Soup over the years to create and train a classification algorithm to predict companies worth giving funding based upon how effective companies with similar data were with the funding in the past. There are 6 questions the data and algorithm answer in the results section below.

## Results:

### Data Preprocessing

1) What variable(s) are considered the target(s) for your model?
    
    * The variable targeted is the IS_SUCCESSFUL data, as this notes whether or not the funds were successfully utilized or not.

![IS_SUCCESSFUL_selection_code](https://user-images.githubusercontent.com/101941048/215592677-92e3aed8-c43a-4097-b96c-0fc46ee11f43.png)

2) What variable(s) are considered to be the features for your model?
    
    * The variables being treated as features are are the: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, INCOME_AMT, and SPECIAL_CONSIDERATIONS data
    
    ![Categorical_Lists](https://user-images.githubusercontent.com/101941048/215592066-50e9101e-b773-41be-82dc-5fff49b4c568.png)
    
3) What variable(s) are neither targets nor features, and should be removed from the input data?
    
    * Neither the NAME nor EIN information are targets nor features, so they have been removed from the input data.

![dropped_EIN_NAME_columns](https://user-images.githubusercontent.com/101941048/215592367-3d4c7538-9bb5-4721-b223-02e3eaa2072a.png)

### Compiling, Training, and Evaluating the Model

4) How many neurons, layers, and activation functions did you select for your neural network model, and why?

    * Using data from the initial model due to it being the best performer: 88 neurons in first hidden layer, 32 neurons in second hidden layer, with "relu" being the hidden layer activation for both and "sigmoid" being the output layer activation function. Adding additional layers and using other activation types did not improve performance, which led to these being chosen.

5) Were you able to achieve the target model performance?

    * I was unable to achieve the target model performance of 75%. All of my trials returned an average of 72%.

6) What steps did you take to try and increase model performance?
  
    * In the first optimization, the step taken to improve performance was to place the ASK_AMT values into bins, no additional changes. In the second optimization, the binned ASK_AMT values were used, the APPLICATION_Type values < 300 were binned (had been <500 before), and the CLASSIFICATION values < 200 were binned (had been <500 before). In the third and final optimization attempt, the binned ASK_AMT values were used, APPLICATION_TYPE and CLASSIFICATION values both returned to <500 being binned, a third hidden layer added, and the hidden layer activation types change from "relu" to "tanh". In all cases, the loss was high and accuracy only 72%. Despite many other attempts, there was an inability to find something to improve the loss and accuracy measures.
  
  ![AlphabetSoupCharity_InitialVSOptimizations_Table](https://user-images.githubusercontent.com/101941048/215591317-664577ac-f3cd-4756-b329-908467d782ff.png)

## Summary and Conclusion:
This model is a starting point, but should be improved upon. At this point in time, it is only able to determine organizations to be effective users of funding just under 3 out of 4 times. Should this model be used to vet companies, executives need to consider whether they are willing to use it knowing it's accuracy and level of loss. 
