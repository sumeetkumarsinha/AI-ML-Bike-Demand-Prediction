# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### SUMEET KUMAR SINHA

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
I had to check for negatives and convert them to 0, then create and submit the csv file.

### What was the top ranked model that performed?

predictor_new_features (WeightedEnsemble_L3)

I tried various models (with different hyperparameters). The best that I could get was one with the new features (datetime split into  month, day, and hour columns with default hyperparameters)

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
I split the datetime column into year, month, day, and hour, and declared the 'weather' and 'season' columns as categoricals.

### How much better did your model preform after adding additional features and why do you think that is?
The score_val went from 52.79 to 30.03, as more useful information was used to train the model.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
Unfortunately, even after trying various combinations of hyperparameters (num_bag_folds,
                                              num_bag_sets,
                                              num_stack_levels,time_limit), I did not get better results.

### If you were given more time with this dataset, where do you think you would spend more time?
I could have experimented with some interaction variables by combining two features to create a new feature.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model       |num_bag_folds |num_bag_sets|num_stack_levels  |score  |
|--          |--            |--          |--                |--     |
|initial     |     0        |    0       |       0          |1.804  |
|add_features|     0        |    0       |       0          |0.6836 |
|hpo         |     7        |    3       |       2          |0.762  |

### Create a line plot showing the top model score for the three (or more) training runs during the project.

Done

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

Done

![model_test_score.png](img/model_test_score.png)



## Summary
This was the first project and it tested various concepts that I learned so far in the course - reading csv files, creating new features, creating and evaluating a model, hyperparameter optimization etc. The data was fairly clean, so that helped in doing this project a little faster. While my results are far from perfect, I am happy I could generate some results in each step. 

