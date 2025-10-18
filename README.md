# Gaussian Elimination
## Developed By:Mirtyunjay .S
## Register Number:212224040190
## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
```
1. Input the number of variables n and augmented matrix a[n][n+1].
2.Perform forward elimination to transform the matrix into upper triangular form.
3.Apply back substitution to solve for unknowns starting from the last equation.
4.Print the solutions for all unknowns.
```
## Program:
```python
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Mirtyunjay.S
RegisterNumber: 212224040190
def gaussian_elimination_no_pivoting(n, entries, eps=1e-12):
    # Build augmented matrix
    A = [list(map(float, entries[i*(n+1):(i+1)*(n+1)])) for i in range(n)]

    # Forward elimination
    for k in range(n):
        pivot = A[k][k]
        if abs(pivot) <= eps:
            raise ValueError("Zero pivot encountered (no pivoting used).")
        for i in range(k+1, n):
            factor = A[i][k] / pivot
            for j in range(k, n+1):
                A[i][j] -= factor * A[k][j]

    # Back substitution
    x = [0.0] * n
    for i in range(n-1, -1, -1):
        rhs = A[i][n]
        for j in range(i+1, n):
            rhs -= A[i][j] * x[j]
        x[i] = rhs / A[i][i]

    return x

# Input
n = int(input())
entries = [float(input()) for _ in range(n*(n+1))]

# Solve
x = gaussian_elimination_no_pivoting(n, entries)

# Output in one line
print(" ".join([f"X{i} = {x[i]:.2f}" for i in range(n)]))

*/
```

## Output:
<img width="1226" height="585" alt="Screenshot 2025-10-18 075304" src="https://github.com/user-attachments/assets/0ad4fed6-f617-4354-9ce9-cb71c5a79efd" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

