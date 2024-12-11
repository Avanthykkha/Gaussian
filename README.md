# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. step 1: input initialization: read th eno. of unknowns n and initialize the augmented matrix of size n(n+1)
2. step2: Forward Elimination: For each row i(from 0 to n-1), ensure the diagonal element a[i][i] is non-zero, eliminate variables below the pivot a[i][i] by mmaking all elements in the same column below i equal to 0 using row operation
3. step 3: check for singular matrix
4. step 4: Back substitution: start from the last row and calculate the value of each variable using the previously solved variables

## Program:

Program to find the solution of a matrix using Gaussian Elimination.

Developed by: Avanthykkha.A.G

RegisterNumber: 24006077
```
import numpy as np
import sys
#Reading number of unknowns
n= int(input())
#making numpy array of n x n+1 size and initializing 
#to zero for storing augmented matrix
a= np.zeros((n,n+1))
#making numpy array of n size and initializing
#to zero for storing solution vector
x= np.zeros(n)
#Reading augmented matrix co-efficients
for i in range(n):
    for j in range(n+1):
        a[i][j]= float(input())
#Applying Gauss Elimination
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
        
    for j in range(i+1,n):
        ratio= a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]= a[j][k]- ratio*a[i][k]

#Back Substitution
x[n-1] = a[n-1][n]/a[n-1][n-1]

for i in range (n-2,-1,-1):
    x[i]= a[i][n]
    for j in range(i+1, n):
        x[i]= x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
#Displaying solution
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]), end=' ')
```

## Output:
![gaussian elimination]()
![Screenshot 2024-12-11 142648](https://github.com/user-attachments/assets/f527c107-c3f5-41bd-b11a-6aabfaec78ad)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

