# 5.0 Simple Regression 

Components of the Regression Line
Whenever we run a correlational analysis, we are trying to determine the strength of the relationship between two variables. An easy way to visualize this is through the use of a scatterplot (see Figure 1 below).

 

![image](https://github.com/Xnrrrrrr/5.0-Simple-Regression/assets/133546385/3c9c79d7-0bd6-491b-bfb3-66929bed68b3)


Example Scatterplot
Figure 1. Scatterplot of the relationship between X and Y.

 

The closer the clumping of the points along a straight line, the stronger the correlation. Oftentimes we fail to see consistency in this clumping due to random errors. Regression analyses involve adding a line of best fit to the data that minimizes the number of errors (or noise) in our predictions.  Our regression line enables us to be able to predict Y just by knowing the value of X. Instead of capturing this value using the mean of Y (Figure 2a), we can more accurately capture it using a continuous line that takes into account the patterns in the relationship between X and Y (Figure 2b).

![image](https://github.com/Xnrrrrrr/5.0-Simple-Regression/assets/133546385/edc3e0ec-4b5a-41b7-b391-705f9321b122)


 

 

Predictions 

Scatter plot with mean line. Dotted lines show the distance between the data points and the mean line Scatter plot with mean line and regression line. Dotted lines show the distance between the data points and the regression line
Figure 2a (left): Using the Mean of Y to predict Y.

Figure 2b (right): Using the regression line to predict Y.

 

When we compare Figure 2a to Figure 2b, we can see that the distance between each data point and its expected value (shown by the solid line) are reduced, therefore the error in our prediction model is also reduced. The method used to create the best fitting regression line is known as the least squares method. This approach finds the regression line that best fits the data by finding the line that has the lowest errors or deviations from the data points.

The main components of the regression line are the intercept, slope, and some measure of error in our estimate, which are summarized in the following equation:

Yi: the outcome that we want to predict
b0: intercept, the value of Y when X = 0
b1: slope, the rate of change in Y for each 1 unit increase in X
Xi: the value our prediction is based on
εi : residual/error term in our prediction model
The parameters b0 and b1 are referred to as the regression coefficients.

 

Please note that when reporting your regression equation you will often leave off the residual/error term. This term is shown in the equation above to highlight the fact that our model will not fit the data perfectly. Once we run our regression analyses and know the values of our intercept and slope, we can then use our regression equation to determine what Y will be when X is a particular value.

 

Using the Regression Line for Predictions
It is fairly simple to use the regression line to make predictions. For example, if we wanted to predict student grades (Y) using class attendance (X), we can represent the line using the following equation: Grades = b0+b1(Attendance) + εi

If after running our regression model we find an intercept of 50 and a slope of 1.5, our final regression equation would be: Grades = 50+1.5(Attendance) + εi

Note: There is no single value for the error term (“ε”) in the equation. We usually provide the error around specific estimates using our prediction or confidence intervals.

 

We can then use our equation to estimate what our outcome would be based on specific values of our predictor. For example, if a student doesn’t attend class, their grade would be 50%: Grades = 50% + 1.5(0) = 50%

Also, if a student attends 20 class sessions their grade would be 80%: Grades = 50% + 1.5(20) = 80%

 

However, we do not have complete certainty on these estimates. Each of these predicted values are associated with some degree of uncertainty that we can represent using our prediction and confidence intervals as discussed below.

 

Prediction and Confidence Intervals
Prediction intervals show the potential range of values for Y, whereas confidence intervals show the potential range of values for the regression line. A confidence interval will therefore be narrower than the prediction interval. Click the interactive image below to see differences in the visualizations of the regression line, prediction interval, and confidence interval. Prediction Intervals are represented by the red boundaries in the visualization below. They show the range of Y values for specific values of X. Whereas, Confidence Intervals are represented by the blue boundaries in the scatterplot. They show the range of the mean of Y for a specific value of X.

 

![image](https://github.com/Xnrrrrrr/5.0-Simple-Regression/assets/133546385/72d4c0ec-638e-4e37-bc6f-0f79f71c33ec)



Use the buttons above to display the linear regression line, confidence interval, and prediction interval for the given scatterplot.

Prediction Interval: Shows the range of Y values for a specific value of X

Confidence Interval: Shows the range of the mean of Y for a specific value of X

Let’s look at an example of this. If we run an analysis and get the following prediction and confidence intervals for our earlier estimate:

When Attendance is 20, Grades = 80
95% Prediction Interval: 70 to 90
95% Confidence Interval: 77 to 83

We could then come to the following conclusions:

Prediction Interval: Our results show that when attendance is 20, 95% of the time grades will fall between 70 to 90.
Confidence Interval: Our results also show that when attendance is 20, 95% of the time the mean grade will fall between 77 to 83.
 

Assessing the Fit of our Regression Model
The two key ways that we assess how well our regression model fits our data is by determining our F-value and our R-Squared coefficient.

The F-value is a ratio of how much the model has improved the prediction of our outcome compared to the level of inaccuracy of the model. A statistically significant F-value has a p-value that is less than .05.
R-Squared tells you the actual proportion of your outcome that can be explained by your predictor. For example, if we tried to predict student grades (Y) using class attendance (X) and found an R2 of 0.25, this would mean that 25% of the variability in grades can be explained by class attendance.
![image](https://github.com/Xnrrrrrr/5.0-Simple-Regression/assets/133546385/dd60c9c4-948d-436d-a14d-321f607a5260)

R-Squared goes by many names. You may hear discussions of the coefficient of determination, the squared multiple correlation coefficient, the degree of overlap, or the shared variability between X and Y. These all refer to the same thing.
The inverse of R-Squared (i.e., 1-R-Squared) is known as the coefficient of non-determination. It tells you how much of the variability in Y is not explained by X.
R-Squared can also be converted to R to determine the strength of the relationship between the predictor(s) and outcome. This can be done by taking the squared root of R-Squared.
Whereas R-squared is the amount of overlap between the predictor and outcome, R is the effect size. This is what we use to evaluate practical significance.
We evaluate effect size using Cohen's cutoffs in which:
less than .10 is a very small effect size/very weak relationship,
.10 to .29 is a small effect size/weak relationship,
.30 to .49 is a medium effect size/moderate relationship, and
.50 or greater is a large effect size/strong relationship.
Please note that when examining a Simple Regression output in the R software, your R-squared value can be found under the "Multiple R-squared" value. We will discuss the Adjusted R-squared value shown in R in the Lesson on Multiple Regression.
 



R Tutorial: Simple Regression in R
In R we use the lm() function to conduct regression analyses. The abbreviation ‘lm’ stands for linear model. The command takes the following form:

newModel = lm(outcome ~ predictor, data = dataFrame, na.action = an action)
lm() function Component
Meaning of each component
newModel

This should be substituted with your name for the new object that will store the results of the regression analysis

lm

Function used to conduct regression analysis.

outcome

This should be substituted with the name of your variable

~

The tilde here means “predicted from”

predictor

This should be substituted with the name of your independent variable

data = dataFrame

Specifies where the data should be taken from. You would substitute ‘dataFrame’ with the name of the object containing your data.

na.action = an action

This is an optional command which tells R how to manage missing values in your dataset. For example, you can exclude missing values from the calculation by stating na.action = na.exclude

 

It is important to know how to build prediction and confidence intervals around our estimates in R. We will use the predict() function for this.

Let’s say we wanted to use our regression model to predict what the sales would be if a record company spent £200,000 on advertising a new album. Given that the units are already in thousands of pounds, we can enter the following value into the predict function for adverts.

Prediction Interval:
predict(albumSales.1, data.frame(adverts = 200), interval = "prediction")
Confidence Interval:
predict(albumSales.1, data.frame(adverts = 200), interval = "confidence")
Note that in the predict() function albumSales.1 represents the object we created earlier to store the results of our regression model, adverts = 200 represents the data point that we’re interested in for our prediction, and “prediction” or “confidence” represent the type of interval we are requesting.

You would report these results as the following:

Prediction Interval: For an investment of £200,000 in advertising, the predicted level of sales would be £153,365, with a 95% prediction interval of £22,666 to £284,063.
Confidence Interval: For an investment of £200,000 in advertising, the predicted level of sales would be £153,365, with a 95% confidence interval of £141,255 to £165,475.
By default, R will report 95% confidence and prediction intervals but this can be adjusted in R. In the syntax below an 80% confidence interval is created around our predicted value of sales when the investment in advertisements is £200,000. This was done by adding the level = .80 argument to the function predict().

predict(albumSales.1, data.frame(adverts = 200), interval = "confidence", level = .80)
