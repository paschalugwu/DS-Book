# Least Squares Regression - Understanding the Line of Best Fit

Least Squares Regression is a statistical method used to find the best-fitting line through a set of points. This line of best fit is a mathematical representation of the relationship between two variables. Let's dive into the core concepts of least squares regression and how it helps us calculate the line of best fit.

## What is Least Squares Regression?

### Definition
Least Squares Regression aims to minimize the sum of the squared differences between the observed and predicted values. It achieves this by fitting a line that best represents the overall trend in the data.

### Line of Best Fit
The line of best fit, also known as the regression line, is the straight line that minimizes the sum of the squared vertical distances (residuals) from each data point to the line. It serves as a predictive model for estimating the dependent variable based on the independent variable.

### Equation of the Line
The equation of the line of best fit is given by:

$$\[ y = mx + b \]

Where:
- $$\( y \) is the dependent variable we aim to predict.
- $$\( x \) is the independent variable used for prediction.
- $$\( m \) is the slope of the line, representing the rate of change.
- $$\( b \) is the y-intercept, indicating the value of $$\( y \) when $$\( x \) is 0.

## How Least Squares Regression Works

1. **Calculate the Mean**
   - Find the mean of both the independent $$(\( \bar{x} \)) and dependent $$(\( \bar{y} \)) variables.

2. **Calculate the Slope (\( m \))**
   - Determine the slope (\( m \)) using the formula:
     \[ m = \frac{\sum_{i=1}^{n} (x_i - \bar{x})(y_i - \bar{y})}{\sum_{i=1}^{n} (x_i - \bar{x})^2} \]

3. **Calculate the Y-Intercept (\( b \))**
   - Calculate the y-intercept (\( b \)) using:
     \[ b = \bar{y} - m \cdot \bar{x} \]

4. **Construct the Line of Best Fit**
   - Form the equation of the line: \( y = mx + b \).

## Real-World Application

Let's apply least squares regression to real-world data. Consider predicting a student's final exam score (\( y \)) based on the number of hours they studied (\( x \)).

### Example Python Code for Least Squares Regression

```python
# Example Python code for least squares regression
import numpy as np
import matplotlib.pyplot as plt

# Sample data: hours studied and exam scores
hours_studied = np.array([2, 4, 6, 8, 10])
exam_scores = np.array([60, 70, 80, 90, 95])

# Calculate mean of hours studied and exam scores
mean_hours = np.mean(hours_studied)
mean_scores = np.mean(exam_scores)

# Calculate slope (m) and y-intercept (b)
m = np.sum((hours_studied - mean_hours) * (exam_scores - mean_scores)) / np.sum((hours_studied - mean_hours) ** 2)
b = mean_scores - m * mean_hours

# Construct the line of best fit
line_of_best_fit = m * hours_studied + b

# Plot the data points and the line of best fit
plt.scatter(hours_studied, exam_scores, label='Data Points')
plt.plot(hours_studied, line_of_best_fit, label='Line of Best Fit', color='red')
plt.title('Least Squares Regression - Exam Scores vs. Hours Studied')
plt.xlabel('Hours Studied')
plt.ylabel('Exam Scores')
plt.legend()
plt.show()
```

This example demonstrates how least squares regression helps create a predictive model for exam scores based on hours studied. The red line represents the line of best fit.

# Least Squares Regression - Mathematical Techniques

Least Squares Regression involves mathematical techniques to find the line of best fit for a set of data points. Let's break down the key mathematical steps used in least squares regression.

## 1. Calculate the Mean

Before diving into least squares regression, we need to calculate the mean of both the independent variable (\(x\)) and the dependent variable (\(y\)).

\[ \bar{x} = \frac{\sum_{i=1}^{n} x_i}{n} \]

\[ \bar{y} = \frac{\sum_{i=1}^{n} y_i}{n} \]

## 2. Calculate the Slope (\(m\))

The slope (\(m\)) of the line of best fit is determined by the formula:

\[ m = \frac{\sum_{i=1}^{n} (x_i - \bar{x})(y_i - \bar{y})}{\sum_{i=1}^{n} (x_i - \bar{x})^2} \]

## 3. Calculate the Y-Intercept (\(b\))

Once we have the slope, we can calculate the y-intercept (\(b\)) using:

\[ b = \bar{y} - m \cdot \bar{x} \]

## 4. Construct the Line of Best Fit

With the slope and y-intercept in hand, we can form the equation of the line:

\[ y = mx + b \]

This equation represents the line of best fit that minimizes the sum of squared differences between observed and predicted values.

## Example Python Code

Let's apply these mathematical techniques to a practical example using Python:

```python
# Example Python code for least squares regression
import numpy as np
import matplotlib.pyplot as plt

# Sample data: hours studied and exam scores
hours_studied = np.array([2, 4, 6, 8, 10])
exam_scores = np.array([60, 70, 80, 90, 95])

# Calculate mean of hours studied and exam scores
mean_hours = np.mean(hours_studied)
mean_scores = np.mean(exam_scores)

# Calculate slope (m) and y-intercept (b)
m = np.sum((hours_studied - mean_hours) * (exam_scores - mean_scores)) / np.sum((hours_studied - mean_hours) ** 2)
b = mean_scores - m * mean_hours

# Construct the line of best fit
line_of_best_fit = m * hours_studied + b

# Plot the data points and the line of best fit
plt.scatter(hours_studied, exam_scores, label='Data Points')
plt.plot(hours_studied, line_of_best_fit, label='Line of Best Fit', color='red')
plt.title('Least Squares Regression - Exam Scores vs. Hours Studied')
plt.xlabel('Hours Studied')
plt.ylabel('Exam Scores')
plt.legend()
plt.show()
```

This Python code demonstrates how to calculate the slope, y-intercept, and construct the line of best fit for a given dataset. The red line in the plot represents the least squares regression line.

# Least Squares Regression - Implementation with Sci-kit Learn

Now that we understand the mathematical foundations of least squares regression, let's explore how to implement it using the popular machine learning library, Sci-kit Learn, in Python.

## Step 1: Import Necessary Libraries

```python
# Import required libraries
import numpy as np
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression
```

## Step 2: Prepare the Data

Assume we have data on the number of hours students study (\(X\)) and their corresponding exam scores (\(Y\)).

```python
# Sample data: hours studied and exam scores
X = np.array([2, 4, 6, 8, 10]).reshape(-1, 1)
Y = np.array([60, 70, 80, 90, 95])
```

## Step 3: Create a Linear Regression Model

```python
# Create a linear regression model
model = LinearRegression()
```

## Step 4: Fit the Model to the Data

```python
# Fit the model to the data
model.fit(X, Y)
```

## Step 5: Make Predictions

Now, we can use the trained model to make predictions. Let's say we want to predict the exam score for a student who studied for 7 hours.

```python
# Make predictions
predicted_score = model.predict([[7]])
print(f'Predicted Exam Score for 7 hours of study: {predicted_score[0]}')
```

## Step 6: Visualize the Line of Best Fit

```python
# Plot the data points
plt.scatter(X, Y, label='Data Points')

# Plot the line of best fit
plt.plot(X, model.predict(X), label='Line of Best Fit', color='red')

# Add labels and legend
plt.title('Least Squares Regression - Exam Scores vs. Hours Studied')
plt.xlabel('Hours Studied')
plt.ylabel('Exam Scores')
plt.legend()

# Show the plot
plt.show()
```

This implementation using Sci-kit Learn simplifies the process of least squares regression. The library takes care of the underlying mathematical details, allowing us to focus on the practical application of building and using the model.

Understanding and applying such tools are crucial for data scientists working on real-world projects, as it streamlines the process of creating accurate predictive models.

© [2024] [Paschal Ugwu]

***AI Use Disclosure:*** *I utilized ChatGPT to assist in the generation and refinement of technical content for this note.*
