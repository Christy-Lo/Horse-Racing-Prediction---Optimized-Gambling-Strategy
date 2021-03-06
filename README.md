# Horse-Racing-Prediction---Optimized-Gambling-Strategy
Groupmate: Chris Yeung

We have collected 10000+ horse-racing records in the past three years with 98 raw features and our random forest model can generate profit of $40K in 3000 races.

## Overview
We aim to build a model that gives an optimized gambling strategy for local horse races, based on the predicted winning horse, the accuracy of the prediction and the win odds. Our model should rely on reasonable features or being interpretable and it outperforms the prediction made by general public. We have constructed a database of the past three years records of the local horse racing result from the Hong Kong Jockey Club website. We have built a Random Forest model with features selection considering the variable importance and the interaction effect between the features and hyperparameter tuning.

There are two notebooks cover the (1)[Web script and Data Analysis](https://github.com/Christy-Lo/Horse-Racing-Prediction---Optimized-Gambling-Strategy/blob/main/Web%20scrap%20and%20EDA.ipynb), (2) [Features selection and model construction](https://github.com/Christy-Lo/Horse-Racing-Prediction---Optimized-Gambling-Strategy/blob/main/Feature%20selection%20and%20model%20comparison.ipynb).

## Experiments
There are many betting games for a horse race and we select two of them.
- Top 1(Win): predict the winning horse in a race
- Top 3(Place): predict 1st, 2nd or 3rd winning horse in a race

In our dataset, each entry of data represents one horse in a race. Some of the variables are win odds, season stakes, rating and draw. Our model gives prediction on whether the horse will be top1 or top3 in the game

For each betting game, we have constructed 4 models and compare their performance.
Target: ‘top1’ flag | Number of features | Accuracy | Net
---|---|---|---
Naive model on ‘top1’ | 64 | 0.9057 | 2
Select features with importance >0.01 | 9 | 0.9026 | 6
Combination: Select the combination of features gives highest accuracy | 14 | 0.9091 | -32
Combination and hyperparameter tuning by grid search | 14 | 0.9029 | 8

Target: ‘top3’ flag | Number of features | Accuracy | Net
---|---|---|---
Naive model  | 64 | 0.7543 | 34933
Select features with importance >0.01 | 9 | 0.748 | 38743
Combination: Select the combination of features gives highest accuracy | 11 | 0.7646 | 41084
Combination and hyperparameter tuning by grid search | 11 | 0.7629 | 36454

## Best Model Performance
Assuming the bet amount is $10 for all the games, if the model makes a correct prediction, the net gain is the (win odd)-1 * 10. If the model make an incorrect prediction, it will lose $10. The best model can predict 40% of the winning race for the bet type ‘Place’ and successfully make more than 40000HKD in 3000 races

For the best model (predicting top3 and adopting "Combination: Select the combination of features gives highest accuracy"),
Total number of betting chance | 2936
---|---
Y3_pred = 1 | 522
Y3_test = 1 | 805
Correct prediction for winning race | 328
Correct prediction for losing race | 1894
Net reward | 41084

## Limitation and solution
Our database is constructed by web scraping and the history of some variables is unavailable on the HKJC website. For example, only current season stakes are shown and this already included the effect of winning, which means we are using the future data to predict the past result. This may mislead the model significantly. We are working on creating web crawlers to collect the data from time to time to avoid bias.

## Acknowledgement
We do not own any of the training or testing data. We have also referred to different tutorials throughout the project and we do not own the code. The links are stated when their codes are adopted.
