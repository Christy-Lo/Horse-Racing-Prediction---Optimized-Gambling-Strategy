# Horse-Racing-Prediction---Optimized-Gambling-Strategy
completed with groupmate: Chris Yeung @[github profile]

We have collected 10000+ horse-racing records in the past three years with 98 raw features and our random forest model can generate profit of $40K in 3000 races.

## Objective of project
We aim to build a model that gives an optimized gambling strategy for local horse races, based on the predicted winning horse, the accuracy of the prediction and the win odds. Our model should rely on reasonable features or being interpretable and it outperforms the prediction made by general publics.

## Highlight of effort
1. We construct a dataset using the past three years records of the local horse racing result from the Hong Kong Jockey Club website.
2. A profiting model using Random Forest is built, with features selection considering the variable importance and the interaction effect between the features. It can predict 40% of the winning race for the bet type ‘Place’ and successfully make more than 40000HKD in 3000 races (bet amount $10)
3. From the NN model built, we discovered that the accuracy of the prediction may not be proportional to the performance of the model, we shall consider the variance of the dataset. Hence, we consider the actual return of the model to evaluate the performance of the model.

## Instruction
There are two jupyter notebook covers the (1)Web scrapt and Data Analysis, (2) Features selection and model construction. 
You might refer the report for the details of the project.
