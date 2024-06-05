# Building-a-xG-model



Expected goal (xG) model is a statistical method used to measure the quality of scoring opportunities in football (soccer).
It assigns a probability value between 0 and 1 to each shot taken during a match, based on factors such as the location of the shot, the type of shot, and the situation leading up to the shot. 
The higher the xG value of a shot, the more likely it is to result in a goal. 

The main factors to consider in this model are the distance to the center of the goal and the angle of the shot, formed by the position of the ball at the time of
the shot and the posts of the goal.


## Distance to goal

The data provided by statsbomb includes the position of the ball at every moment of the game, this includes the position at the moment of the shot
Using the x and y coordinates in the pitch we can define a function to calculate the distance. Knowing that the dimensions of the pitch are 120x80
is clear that the center of the goals are located on the point (120, 40)
So we have two points which we can transform into a vector and simply calculate its norm using the math library of python.


## Angle to goal 

Now we want to find the angle formed by the posts and the ball at the moment of the shot. Drawing two vectors from the ball position to each post, we can find the angle formed by 
them using the dot product from Linear Algera.


## Collecting the information

Using the data provided by Statsbomb, we collected data from the competition La Liga of the season 2018-2019.
Collecting information of all matches we obtained several data useful for our model.

Filtering the data of the shots we obtained the location, and by adding simple parameters as the pressure of the rivals we trained our model using different 
models of Machine Learning.

## Models 

Looking for the better prediction, four models were used:
* Logistic Regression
* Naive-Bayes
* K-Neighbors Classifier
* Support Vector Classifier

Each one was trained with the same data and its accuracy was computed, along with their Learning Curve

Finally it was decided to choose the Logistic Regression model to predict or xG values.
Defining a function with all the parameters we can now use our model in different projects.







