# Deep Learning: Charity Funding Predictor
## Intent
Utilizing deep learning and neural networks, I examined charity data provided by AlphabetSoup to determine if applicants would be successfully funded given that 34,000 organization were previously successful. 

## Data Processing
For the initial model, I removed the irrelevant data; this meant I dropped the  “EIN” and “NAME” columns. The remaining columns and their data were considered features for the model. I will state that I did add “NAME” back in the second run and will explain my reasoning. For the “CLASSIFICATION” and “APPLICATION_TYPE” columns, I counted the number of occurrences to allow for binning and better data model processing. In each case, I grouped rare occurrences into an “Other” category by setting a cut-off value and verified that the binning was successful.
The target variable for the model used the values from the “IS_SUCCESSFUL” column where a value of “1” indicated a “yes” and “0” indicated a “no. I then used the “pd.get_dummies()” function to encode any other categorical variables and applied StandardScaler to further transform the data to attempt to optimize the run and meet the targeted predictive accuracy of 75%. Once processed, I split the data into training and testing sets.

## Compiling, Training, and Evaluating the Model
For each model, I applied a multi-layered neural network with the first utilizing two. The number of features dictated the number of hidden nodes. The first model generated 8,191 parameters and an accuracy score of 73.1% when run 100 times. Screenshots of the first model results are below.
![image](https://user-images.githubusercontent.com/104914008/202579186-84a38c0d-9cb1-49a9-b0e4-5c5b9343399a.png)
![image](https://user-images.githubusercontent.com/104914008/202579164-bbf64984-179d-4c1e-aa10-b34c593fd0a0.png)

### Results of First Model:
![image](https://user-images.githubusercontent.com/104914008/202579138-a53ecb0d-fc49-47fa-853c-b0b33ae6bca4.png)

## Optimization
Since the initial model failed to hit the target accuracy score, I added the “NAME” column back into the dataset and performed the same methods as in the first model for a second attempt. I also added a hidden layer and increased the nodes which resulted in 482,817 parameters. This time, the model produced an accuracy score of 79.55%. Screenshots of the second model results are below.
![image](https://user-images.githubusercontent.com/104914008/202579118-d86b4830-89c5-4e9d-97d2-878703712282.png)
![image](https://user-images.githubusercontent.com/104914008/202579104-12bca046-e33a-4c42-b63b-0f661a448c4a.png)

### Results of Second Model:
![image](https://user-images.githubusercontent.com/104914008/202579090-65413dde-6f04-436f-9091-8b31aaf31837.png)

