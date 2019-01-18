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


