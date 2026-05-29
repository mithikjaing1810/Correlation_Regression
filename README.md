# Correlation and regression for data analysis
# Aim : 

To analyse given data using coeffificient of correlation and regression line
![image](https://user-images.githubusercontent.com/104613195/168224136-d6b64e64-7d3d-4775-9337-c8f96fe41f2d.png)


# Software required :  

Python

# Theory:

Correlation describes the strength of an association between two variables, and is completely symmetrical, the correlation between A and B is the same as the correlation between B and A. However, if the two variables are related it means that when one changes by a certain amount the other changes on an average by a certain amount.  

If y represents the dependent variable and x the independent variable, this relationship is described as the regression of y on x. The relationship can be represented by a simple equation called the regression equation. The regression equation representing how much y changes with any given change of x can be used to construct a regression line on a scatter diagram, and in the simplest case this is assumed to be a straight line.

# Procedure :

![image](https://user-images.githubusercontent.com/104613195/168225866-ac8f6610-bdc3-4ac2-a24e-2b24ba08e189.png)

# Program :
```

import matplotlib.pyplot as plt
import numpy as np
import math

# Input values
x = np.array([25, 28, 35, 32, 31, 36, 29, 38, 34, 32])
y = np.array([43, 46, 49, 41, 36, 32, 31, 30, 33, 39])

N = len(x)

Sx = 0
Sy = 0
Sxy = 0
Sx2 = 0
Sy2 = 0

# Calculations
for i in range(0, N):
    Sx = Sx + x[i]
    Sy = Sy + y[i]
    Sxy = Sxy + x[i] * y[i]
    Sx2 = Sx2 + x[i] ** 2
    Sy2 = Sy2 + y[i] ** 2

# Correlation coefficient
r = (N * Sxy - Sx * Sy) / (
    math.sqrt(N * Sx2 - Sx ** 2) *
    math.sqrt(N * Sy2 - Sy ** 2)
)

print("The Correlation coefficient is %.3f" % r)

# Regression coefficient
byx = (N * Sxy - Sx * Sy) / (N * Sx2 - Sx ** 2)

# Mean values
xmean = Sx / N
ymean = Sy / N

# Regression line
print("The Regression line Y on X is :")
print("y = %.3f + %.3f (x - %.3f)" % (ymean, byx, xmean))

# Scatter plot
plt.scatter(x, y)

# Regression function
def Reg(x):
    return ymean + byx * (x - xmean)

# Regression line values
x1 = np.linspace(min(x), max(x), 100)
y1 = Reg(x1)

# Plot regression line
plt.plot(x1, y1, 'r')

# Labels
plt.xlabel('x-data')
plt.ylabel('y-data')

# Legend
plt.legend(['Regression Line', 'Data points'])

# Grid
plt.grid(True)

# Show graph
plt.show()

```
# Output 
<img width="872" height="549" alt="image" src="https://github.com/user-attachments/assets/6234bcba-bc3d-4c18-8953-8a6cdb906337" />


# Result
The coefficient of correlation and regression line for the given data are calculated successfully using Python.

