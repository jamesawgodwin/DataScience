# Explain Collinearity to a college student

### High Level
in statistics is a phenomenon when one or more of the predictor variables in a multiple regression model can be linearly predicted from another predictor variable, also can say they are highly correlated

### Low Level with Example
an example of this could be building a model that predicts heating costs in a building that you were gonna build and we have a bunch of inputs like the area of the building, the number of floors, the height, the weather infor etc. There is a strong relationship between number of floors and the height of a building - more floors a building has the greater the height. Collinearity is not good or bad, is just part of the **exploratory data analysis and model building process** Because of the collinearity it might be possible to remove one of those two, but an example where you might want to leave both collinear variabe in is considering the ratio of the building height to the number of floors and considering how that **ratio** would change for **residential vs commencial vs multipurpose building**. Model weights could also be affected by having collinear variables.

**EXAMPLE FROM PERSONIFY EXPERIENCE**

# Explain Begin Statistics and Machine Learning

## Open-ended question
A very debated topic. Some people believe that ML is a subset of statistics or is built on statistical theory
in statistics you want to **test hypotheses**. An example is do right-handed batters hit more homeruns than lefthanded
batters in baseball. **We can collect the data and do a statistical test to reject the null hypothesis** - a fancy
way of saying "is there a difference?" Statistics tends to simplify the data, and often times models are linear
because of this simplification. For instance, the treatment of outliers is very important in statistics. Where 
in **ML the focus is on predictions**, more generally. Continuing with the baseball example ML can help answer the
question of what is the probability of a given batter hitting a homerun off a certain pitcher in a certain inning.
You need a lot more data and a lot more inputs. Statistics likes linear models where as in ML there are classes
of algorithms that can handle a lot more complexity, a lot more inputs. The downside to that is that complex ML model may have thousands or even millions of parameters. 

**ML and statistics are used to solve different problems**. 

## What are parameters and linear regression? Answer for a manager - what is the right level of complexity?
With statistics we tend to be happy with smaller data sets, statistical tools tend to struggle with larger datasets.
With ML you absolutely have to have large datasets, and ML models tend to break down with small datasets.
A simple way of differentiating whether to use statistics or ML to solve a problem is to look at the amount and complexity
of the information you have and want to model. Both come down to modeling data ultimately.

# Coding question: Write a function which tells you which rows in a column contain an outlier. Use any language youl ike but be prepared to justify your choice.

## I choose R because it sounds like the data will be in a dataframe, which you have to use Pandas for in python, but in R they are a first class object.

### an assumption I make is that 'significance' is defined as +- 1.5 sd, but the variable i created can easily be amended

rows_with_outliers <- function(column, how_man_sds = 1.5) {

  //maximum and minimum value that's not an outlier
  max <- mean(column) + (1.5 * how_many_sds(column))
  min <- mean(column) - (1.5 * how_many_sds(column))
  
  //look in the column and see which rows are below the min or above the max
  
  outliers <- column %>% 
    mutate(outliers = (column < min | column > max))
    select(outliers)
  //return a boolean vector with those rows
    
    return(outliers)

}
 # Second Question

## Working with a vet, you have a dataset that contains the info on the horses that they have treated - you are asked to help design a model that predicts if horse needs surgery. The data file contains some missing values. How do you proceed?

First thing that could be done is that you could drop all rows that contain a missing value (NA), and this is ideal when thre are only one or two missing values. If there are many NA/nulls and the variable is numeric imputation is possible whereby you average the other values for a given column or category and use the average value for that NA - an example is the rectal temperature of the horse - given only a couple NA's the averge imputed value is useful. For a categorical variable, such as abdominal distension, stomach bigness, you could use the most common value, assuming that abdominal distension is rare.

An important part of Data Science is interfacing with the owner of the data. I would ask if my assumptions about the data from the previous paragraph are true - after all the vet is the domain expert on horses and can guide my treatement of missing values in the data set. Not all NAs are the same - the data could be missing, corrupt, or in the case of a healthy horse, not present. The specialized knowledge of the vet will determine if we need a separate dataframe structure, like a branching decision tree where if there is nasogastric reflux we need to worry about the pH and if there isn't we don't. Working with the veterinarian is the best way to build the most robust possible model for this data set.


# Third Question

## When using imputation should you use the median or the mean of the data?

A bad joke goes - when Bill Gates walks into the bar the average bar patron becomes a millionaire! Haha but this demonstrates the danger of using the mean when calculating imputation - **it can skew your data**. Replacing missing data with the average can result in an artificially high number for them, where as with the median you are more likely to get data that reflects the general population.

# Fourth Question

## Explain the distinction between REGRESSION and CLASSIFICATION

Regression is used when you are trying to predict a continuous output/variable, like temperature, salary, or stock price: there are infinitely many values. Classification is when you predict a predefined category or class - e.g., is a sample participant male or female.

For regression, the way to evaluate the model performance is with a metric called RMSE (Root Mean Squared Error). It is calculated as the root of the mean of the squared differences between the predictions and the real values.

However, for things like stock price prediction, evaluating the model with the RMSE does not make much sense, since we are more interested in the directions taken by our predictions, rather than the closeness of their values to the real stock price. We want to check if our predictions follow the same directions as the real stock price

# What is supervised machine learning? 👶
Training the machine with data that is previously labeled - the opposite is unsupervised where the machine looks for clusters/associations in the data for groups to give labels to.
## Regression:predict a single (continuous) output value using training data.
Example: You can use regression to predict the house price from training data. The input variables will be locality, size of a house, etc.
## Classification: group the output inside a class. 
If the algorithm tries to label input into two distinct classes, it is called binary classification. Selecting between more than two classes is referred to as multiclass classification.
Example: Determining whether or not someone will be a defaulter of the loan.
Strengths: Outputs always have a probabilistic interpretation, and the algorithm can be regularized to avoid overfitting.
Weaknesses: Logistic regression may underperform when there are multiple or non-linear decision boundaries. This method is not flexible, so it does not capture more complex relationships.

# What is regression? Which models can you use to solve a regression problem? 👶


# What is linear regression? When do we use it? 👶

# What’s the normal distribution? Why do we care about it? 👶

# How do we check if a variable follows the normal distribution? 👩‍🎓

# What if we want to build a model for predicting prices? Are prices distributed normally? Do we need to do any pre-processing for prices? 👩‍🎓

# What are the methods for solving linear regression do you know? 👩‍🎓

# What is gradient descent? How does it work? 👩‍🎓

# What is the normal equation? 👩‍🎓

# What is SGD - stochastic gradient descent? What’s the difference with the usual gradient descent? 👩‍🎓

# Which metrics for evaluating regression models do you know? 👶

# What are MSE and RMSE? 👶

# What is overfitting? 👶

# How to do you validate your models? 👶

# Why do we need to split our data into three parts: train, validation, and test? 👶

# Can you explain how cross-validation works? 👶

# What is K-fold cross-validation? 👶

# How do we choose K in K-fold cross-validation? What’s your favourite K? 👶

# What happens to our linear regression model if we have three columns in our data: x, y, z - and z is a sum of x and y? 👩‍🎓

# What happens to our linear regression model if the column z in the data is a sum of columns x and y and some random noise? 👩‍🎓

# What is regularization? Why do we need it? 👶

# Which regularization techniques do you know? 👩‍🎓

# What is classification? Which models would you use to solve a classification problem? 👶

# What is logistic regression? When do we need to use it? 👶


# Is logistic regression a linear model? Why? 👶

# What is sigmoid? What does it do? 👶

# How do we evaluate classification models? 👶

# What is accuracy? 👶

# Is accuracy always a good metric? 👶

# What is the confusion table? What are the cells in this table? 👶

# What is precision, recall, and F1-score? 👶

# Precision-recall trade-off 👩‍🎓

# What is the ROC curve? When to use it? 👩‍🎓

# What is AUC (AU ROC)? When to use it? 👩‍🎓

# How to interpret the AU ROC score? 👩‍🎓

# What is the PR (precision-recall) curve? 👩‍🎓

# What is the area under the PR curve? Is it a useful metric? 👩‍🎓

# In which cases AU PR is better than AU ROC? 👩‍🎓

# What do we do with categorical variables? 👩‍🎓

# Why do we need one-hot encoding? 👩‍🎓

# What kind of regularization techniques are applicable to linear models? 👩‍🎓

# How does L2 regularization look like in a linear model? 👩‍🎓

# How do we select the right regularization parameters? 👶

# What’s the effect of L2 regularization on the weights of a linear model? 👩‍🎓

# How L1 regularization looks like in a linear model? 👩‍🎓

# What’s the difference between L2 and L1 regularization? 👩‍🎓

# Can we have both L1 and L2 regularization components in a linear model? 👩‍🎓

# What’s the interpretation of the bias term in linear models? 👩‍🎓

# How do we interpret weights in linear models? 👩‍🎓

# If a weight for one variable is higher than for another - can we say that this variable is more important? 👩‍🎓

# When do we need to perform feature normalization for linear models? When it’s okay not to do it? 👩‍🎓

# What is feature selection? Why do we need it? 👶

# Is feature selection important for linear models? 👩‍🎓

# Which feature selection techniques do you know? 👩‍🎓

# Can we use L1 regularization for feature selection? 👩‍🎓

# Can we use L2 regularization for feature selection? 👩‍🎓

# What are the decision trees? 👶

# How do we train decision trees? 👩‍🎓

# What are the main parameters of the decision tree model? 👶

# How do we handle categorical variables in decision trees? 👩‍🎓

# What are the benefits of a single decision tree compared to more complex models? 👩‍🎓

# How can we know which features are more important for the decision tree model? 👩‍🎓

# What is random forest? 👶

# Why do we need randomization in random forest? 👩‍🎓

# What are the main parameters of the random forest model? 👩‍🎓

# How do we select the depth of the trees in random forest? 👩‍🎓

# How do we know how many trees we need in random forest? 👩‍🎓

# Is it easy to parallelize training of random forest? How can we do it? 👩‍🎓

# What are the potential problems with many large trees? 👩‍🎓

# What if instead of finding the best split, we randomly select a few splits and just select the best from them. Will it work? 🛠️
