- Statistical technique used to find the relationship between variables
Eg: Predict a car's fuel efficiency:

| Pounds in 1000s | Miles per gallon |
| --------------- | ---------------- |
| 3.5             | 18               |
| 3.69            | 15               |
| 3.44            | 18               |
| 3.43            | 16               |
|                 |                  |
![[linear regression1.1.excalidraw]]
# Linear Regression Equation

The Linear Regression model would be defined as $\boxed{y=mx+b}$.
where,
![[linear regression-1.2.excalidraw]]
### Models with multiple features
Suppose if the model for predicting a car's efficiency also depended on factors other than *pounds* like *Engine displacement*, *acceleration, number of cylinders* and *horsepower*. This model would be written as:
$$
y = b+w_{1}x_{1} + w_2x_2 + w_3x_3 + w_4x_4 + w_5x_5
$$
