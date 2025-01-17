# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import numpy library using import statement.
2. Import sys library
3. Create a variable n to recieve to recieve dimention of the matrix.
4. using input n,create a zero matrix 'a' of nx(n+1) and a zero row matrix 'x' of n using np.zeros().
5. Initiate 1st nested for loop to get values from user and store it in the 'a' matrix using float(input()).
6. Initiate 2nd nested for loop to apply gaussian elimination.
7. Initiate 3rd nested for loop to calculate the solution of the 'a' matrix using back substitution.
8. Display the solution for each variable upto 2 decimals using for loop and print() with '%' operator.

## Program:
```
/*
'''Program to solve a matrix using Gaussian elimination with partial pivoting.
Developed by: vidya neela
RegisterNumber: 21500298
'''
import numpy as np
import sys
n = int(input())
a = np.zeros((n,n+1))
X = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by zero detected')
    for j in range(i+1, n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
X[n-1] = a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    X[i] = a[i][n]
    for j in range(i+1,n):
        X[i] = X[i] - a[i][j]*X[j]
    X[i] = X[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' %(i,X[i]), end = ' ')
*/
```

## Output:
![gaussian elimination](./output.jpg)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

