# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the numpy module to use the built-in functions for calculation
2. Use zeros() function to create two null matrices a and x
3. use "for" loop for inputing values for a matrix and reducing the a matrix to row-echelon form
4. once again use "for" loops to solve the a matrix and  find the values of x matrix, which is the solution 
5. End the program

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: yuvan raj R
RegisterNumber: 25014899
*/
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j]==0:
        sys.exit('divide by zero detected')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')
```

## Output:
![gaussian elimination]()

<img width="788" height="460" alt="Screenshot 2025-10-17 111037" src="https://github.com/user-attachments/assets/70b41154-e736-49b7-9f13-b33df5b99289" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

