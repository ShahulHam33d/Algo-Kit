# Linear regression using OLS: The Traditional Way
If you've spent time watching YouTube tutorials or reading blog posts about linear regression, you might feel like you understand how the algorithm works. Most resources out there often introduce you to Gradient Descent, a popular optimization technique. But here's the thing: while Gradient Descent is useful, it's not the original or most common method used for linear regression.
So, this brings up an important question: Do you really understand linear regression?
I asked myself this very question. Even though I had a good grasp of the algorithm, I realized I was missing some fundamental concepts. The traditional method for linear regression is actually called Ordinary Least Squares (OLS), and it's crucial to understand how it works before diving into more advanced techniques like Gradient Descent. So, I dug deep into the OLS, breaking down each step to its core, and finally found the answers I was looking for.
In this article, I'll walk you through the essentials behind OLS, share the questions that popped into my head along the way, and guide you to the answers. We'll also run the code in Python, comparing our approach to the sklearn.linear_model.LinearRegression function, which uses OLS by default. Let's dive in and make sure we've got the basics down!
Intro: Linear regression is a method to find the best straight line that represents your data on a graph. Every line on a graph has an equation that describes it, and the line we're interested in is called the 'line of best fit.' The equation for this line is y = mx + b. Recognize it? That's the slope-intercept form, and it's a real game-changer. To truly understand linear regression, it's key to revisit this formula.
So, what makes a line the "best fit"?
In a graph with thousands of data points, the best-fit line should:
Come as close as possible to the most points.
Balance the points, with about the same number above and below.
Minimize the distance between the line and all the points.

The equation y=mx+b is like a secret code that helps us find our main objective
y is the dependent variable, the thing we're trying to predict.
x is the independent variable, the thing we're using to make predictions.
m is the slope, which tells us how steep the line is.
b is the y-intercept, the point where the line crosses the y-axis.

It's all about understanding how these pieces work together to unlock the solution.
Now that we know what we need:
Goal: Minimize the sum of squared errors (SSE) between predicted and actual values.
Objective: Find m (slope) and b (intercept).
In Gradient Descent:
We start by randomly initializing mmm and b.
Compute the SSE for the current mmm and b.
Calculate the partial derivative of SSE with respect to m and b.
Repeat these steps until convergence or a stopping criterion is met.

This is one way to find the best values for m and b. But when using Ordinary Least Squares (OLS), there's a closed-form solution that avoids the iterative process of gradient descent.
To find mmm and b using OLS, you can use these formulas:
For m (slope):

m = (mean(xy) - mean(x) × mean(y)) / (mean(x²) - (mean(x))²) 

For b (intercept):

b = mean(y) - m × mean(x) 

There's a more formal version of this using summation notation, but I prefer sticking with the mean notation since it's simpler. All we need is these two formulas and apply in it another formula for prediction.

prediction (y):

y = mx + b
