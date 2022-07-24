# Quora Question Pair Similarity

Over 100 million people visit Quora every month, so it's no surprise that many people ask similarly worded questions. Multiple questions with the same intent can cause seekers to spend more time finding the best answer to their question, and make writers feel they need to answer multiple versions of the same question. Quora values canonical questions because they provide a better experience to active seekers and writers, and offer more value to both of these groups in the long term.  so main aim of project is that predicting whether pair of questions are similar or not. This could be useful to instantly provide answers to questions that have already been answered.
   Credits: Kaggle
### Problem Statement:
Identify which questions asked on Quora are duplicates of questions that have already been asked.

### Real world/Business Objectives and Constraints:
   - The cost of a mis-classification can be very high.
   - You would want a probability of a pair of questions to be duplicates so that you can choose any threshold of choice.
   - No strict latency concerns.
   - Interpretability is partially important.

### Performance Metric:
   - log-loss 
   - Binary Confusion Matrix

### Data Overview:
Train.csv contains 5 columns : qid1, qid2, question1, question2, is_duplicate. Total we have 404290 entries. Splitted data into train and test with 70% and 30%.

### Machine Learning Models and Conclusion:
- First, we have build a random model, which generates a test log loss as 0.8847. Now, we can use this score as benchmark for other models to compare. If a model has above this score, then it is a bad model.

- As the model 1 to train and test the data, we have used logistic regression that gives train loss as 0.42065 and test loss as 0.42206, which is a good score for a start.

- Next, we have used linear SVM that gives test loss as 0.43915, which is low than logistic regression that indicates logistic regression is a better model still.

- Finally, we have used XGBoost as our model, that gives 0.31802 as test loss, which much lower than logistic regression. So, now we conclude XGBoost is our best model.

- After three models, we can say XGBoost is our best model with 0.31802 as test loss. And no model's score is above random model.

### References:
1. https://www.kaggle.com/c/quora-question-pairs 
2. https://github.com/seatgeek/fuzzywuzzy#usage , https://chairnerd.seatgeek.com/fuzzywuzzy-fuzzy-string-matching-in-python/
3. http://proceedings.mlr.press/v37/kusnerb15.pdf
