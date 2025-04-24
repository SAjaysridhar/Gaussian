# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
Step 1:<br>
Import the required libraries numpy and sys.

Step 2:
Input the size of the matrix n and define augmented matrix a as a NumPy array of size (n, n+1). Initialize the solution array x as a NumPy array of size n.

Step 3:
Perform forward elimination to transform the augmented matrix into an upper triangular form:

For each pivot row, ensure the pivot element is non-zero.
Subtract multiples of the pivot row from the rows below to eliminate the elements below the pivot.

Step 4:
Perform backward substitution to compute the solution:

Start with the last variable and substitute back into the equations to find the remaining variables.

Step 5:
Display the solution values of all variables using formatted output.

Step 6:
Verify the results for correctness.

## Program:<br>

'''Program to solve a matrix using Gaussian elimination without partial pivoting.<br>
Developed by  : AJAY S<br>
RegisterNumber: 212224230010<br>
'''

import numpy as np<br>
import sys<br>
n=int(input())<br>
a=np.zeros((n,n+1))<br>
x=np.zeros(n)<br>

for i in range(n):<br>
    for j in range(n+1):<br>
        a[i][j]=float(input())<br>
        
for i in range(n):<br>
    if a[i][i]==0.0:<br>
        sys.exit('Divide by zero detected!')<br>
    for j in range(i+1,n):<br>
        ratio=a[j][i]/a[i][i]<br>
        for k in range(n+1):<br>
            a[j][k]=a[j][k]-ratio*a[i][k]<br>
x[n-1]=a[n-1][n]/a[n-1][n-1]<br>

for i in range(n-2,-1,-1):<br>
    x[i]=a[i][n]<br>
    for j in range(i+1,n):<br>
        x[i]=x[i]-a[i][j]*x[j]<br>
    x[i]=x[i]/a[i][i]<br>
for i in range(n):<br>
    print('X%d = %0.2f'%(i,x[i]),end=" ")<br>

## Output:
![gaussian elimination]()
![Screenshot 2025-04-24 214231](https://github.com/user-attachments/assets/4d66d3dc-0b7c-4586-a9f7-e76b312392f8)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

