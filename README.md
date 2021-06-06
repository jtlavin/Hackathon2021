# Hackathon2021-ML-Project
The objective of this work was to predict, within a telecommunications company, if a customer would upgrade his mobile device, i.e. if, for example, he had an iPhone 6, to determine if the customer would be willing to purchase a newer model iPhone such as an iPhone 8 or an iPhone 10.
10 files were provided with different variables each, within which each customer could be identified by a unique line_id.
By means of these files and the information recorded in the activity, data and behavior of each customer, a predictive model had to be made to achieve the desired result, having as final result or deliverable a file with two columns: in the first one, the customer's line_id and in the second one a 0 or a 1 that indicates whether the customer will upgrade or not.

## exploratory analysis

The purpose of the analysis was to detect variables that could be eliminated or transformed to provide simpler information to the model, such as grouping variables into categories or eliminating variables with low variability. Two functions were used for this purpose, one for categorical variables and the other for numerical variables. These functions apply a criterion to each column of the dataset and based on that criterion we decide whether that variable constitutes noise:

  1. Numerical cleaner: A variable constitutes noise if its maximum and minimum coincide.
  2. Categorical cleaner: A variable constitutes noise if it has only one category or if one category accounts for more than 95% of the data.

It should be noted that not all the variables found in these criteria were eliminated, since in some cases it was intuited that they could provide information.

## Modeling

Principal component analysis (PCA) was performed to ensure that the selected variables contained considerable variability. In combination with this, a recursive feature elimination with cross validation process was performed to obtain the optimum number of features. Results show that the model would not be very efficient with more than 15 features, so this base was already taken as the maximum number of features to choose.

Once the features were selected, the data were entered into the model, being the one used on this occasion a Support Vector Machine. It was decided to use this model after an extensive number of tests with other models, such as random forest, XG Boost, Gradient Boost, Ada Boost, among others. Among all the models, SVM presented the best results due to its generalization capacity, so this model was selected to respond to the problem posed. In the tests performed, accuracy results of more than 90% were obtained with random forests, which was later verified to be simply performing a very strong overfit on the data presented. The SVM obtained results of 80% and were identical to the f1_score from the judges.
