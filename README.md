# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Start

2.Read the number of variables n.

3.Input the augmented matrix of size n x (n+1).

4.Forward Elimination:

  Convert the matrix to upper triangular form.

  For each row below the current row:

Eliminate the variable using row operations.

5.Back Substitution:

   Start from the last equation and solve for the variables one by one.

   Display the values of all variables (X0, X1, ..., Xn-1).

6.End

## Program:

'''Program to solve a matrix using Gaussian elimination without partial pivoting.

Developed by: Deepika.V

RegisterNumber: 24000724

'''
import numpy as np

import sys

n = int(input())

a = np.zeros((n, n+1))

x = np.zeros(n)

for i in range(n):

    for j in range(n + 1):
 
        a[i][j] = float(input())

for i in range(n):
  
    if a[i][j] == 0.0:

    sys.exit("Divide by zero detected!")

for j in range(i +1, n):

    ratio = a[j][i]/a[i][i]
        
    for k in range(n+1):
        
        a[j][k] = a[j][k]- ratio * a[i][k]

x[n-1] = a[n-1][n]/a[n-1][n-1]

for i in range(n-2, -1,-1):

   x[i] = a[i][n]
    
   for j in range(i+1, n):
    
       x[i] = x[i] - a[i][j] * x[j]
    
   x[i] = x[i]/a[i][i]
    

for i in range(n):

    print('X%d = %0.2f' %(i,x[i]), end=" ")

output:

![Screenshot 2025-04-27 133011](https://github.com/user-attachments/assets/7b743024-0451-47c4-8479-82cf8a25d584)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.


```


