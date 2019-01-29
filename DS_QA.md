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




