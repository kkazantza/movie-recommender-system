# Movie Recommender System using serendipity concept
The goal of this project is to create a recommender system which helps users find items in a way that maximizes the amount of serendipity in the system. This means that this part consists of two basic parts; the former refers to defining “serendipity” concept and creating a method of predicting serendipity and the latter to solving an optimization problem for maximizing the serendipity in the system.

### Feature Engineering for Serendipity Prediction Model

1. Genre-based similarity to user profile
2. Tag-based similarity to user profile
3. Popularity
4. Predicted Rating

### Serendipity models
1. Logistic Regression Model

   In this approach, we faced the problem of predicting serendipity index as a binary classification problem. Serendipity index is a binary variable, taking value 1 if the item is    considered serendipitous for the user, or value 0 if the item is not considered serendipitous for the user. 
   **For the model training, we computed serendipity index(0 or 1) in a per user-per item level from “answers.csv” as the union of the 6 attributes “s_ser_find’, “s_ser_imp”,        “s_ser_rec”, “m_ser_find”, “m_ser_imp”, “m_ser_rec”**

2. Random Forest for Supervised Regression

   A random forest is an ensemble model that consists of many decision trees. Predictions are made by averaging the predictions of each decision tree. At this attempt to predict      the serendipity index for every (user, movie) pair in the answers.csv dataset we set the target as a continuous variable. 
   **The target serendipity index is defined as the average of answers of users to questions s5,s6,s7.**


### Optimization Problem

1. Recompute the features for all the users for the movies that have not seen - rated.
2. Predict Serendipity for all possible (user, movie) pairs by using the two candidate models as in training phase, Logistic Regression and Random Forest model.
3. Optimization

   The goal is to maximize the total average serendipity to users.
