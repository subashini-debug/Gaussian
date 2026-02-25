# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1️⃣ Form the augmented matrix 
[
𝐴
∣
𝐵
]
[A∣B].

2️⃣ Perform forward elimination to convert the matrix into upper triangular form.

3️⃣ Use back substitution starting from the last equation.

4️⃣ Obtain the solution vector 
𝑋

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Subashini K
RegisterNumber: 212225240160
'''
```
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
 for j in range(n+1):
   a[i][j]=float(input())
for i in range(n):
   if a[i][j]==0.0:
     sys.exit('divide by zero detected!')

   for j in range (i+1,n):
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
  print("X%d = %.2f"%(i,x[i]), end=" ")

```

## Output:

<img width="1920" height="1080" alt="Screenshot (202)" src="https://github.com/user-attachments/assets/4d100bb3-1700-4083-84a3-698646782777" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

