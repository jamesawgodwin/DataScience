# Explain Collinearity to a college student

### High Level
in statistics is a phenomenon when one or more of the predictor variables in a multiple regression model can be linearly predicted from another predictor variable, also can say they are highly correlated

### Low Level with Example
an example of this could be building a model that predicts heating costs in a building that you were gonna build and we have a bunch of inputs like the area of the building, the number of floors, the height, the weather infor etc. There is a strong relationship between number of floors and the height of a building - more floors a building has the greater the height. Collinearity is not good or bad, is just part of the **exploratory data analysis and model building process** Because of the collinearity it might be possible to remove one of those two, but an example where you might want to leave both collinear variabe in is considering the ratio of the building height to the number of floors and considering how that **ratio** would change for **residential vs commencial vs multipurpose building**. Model weights could also be affected by having collinear variables.

**EXAMPLE FROM PERSONIFY EXPERIENCE**

