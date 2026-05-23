# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

Step 1: Import the NumPy library using import numpy as np.

Step 2: Define the coefficient matrix and constant matrix using np.array().

Step 3: Apply Gaussian Elimination to convert the matrix into row echelon form and solve the system of equations.

Step 4: Display the solution of the matrix using the print() function.

## Program:
```

Program to find the solution of a matrix using Gaussian Elimination.
Developed by: SARANYA R
RegisterNumber:212225040384

import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
def solve_gaussian(data):
    n=int(data[0])
    A=np.array(data[1:],dtype=float).reshape(n,n+1)
    for i in range(n):
        for j in range(i+1,n):
            factor=A[j,i]/A[i,i]
            A[j]-=factor*A[i]
    x=np.zeros(n)
    for i in range(n-1,-1,-1):
        x[i]=(A[i,-1]-np.dot(A[i,i+1:n],x[i+1:n]))/A[i,i]
    return x
data=[]
for i in range(13):
    data.append(input())
result=solve_gaussian(data)
print("".join([f"X{i} = {val:.2f} "for i,val in enumerate(result)]))

```

## Output:
<img width="1015" height="597" alt="image" src="https://github.com/user-attachments/assets/a0c794a9-48be-4f28-99aa-6b34676a01f4" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

