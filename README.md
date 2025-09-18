# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```python
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: C Dharshan
RegisterNumber: 212224230059
'''
import numpy as np
def QR_Decomposition(A):
    m,n=A.shape
    Q=np.empty((m,n))
    R=np.zeros((n,n))
    for j in range(n):
        v=A[:,j]
        for i in range(j):
            q=Q[:,i]
            R[i,j]=np.dot(q,v)
            v=v-R[i,j]*q
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
    print("The Q Matrix is\n",Q)
    print("The R Matrix is\n",R)
a = np.array(eval(input()))
QR_Decomposition(a)

```

## Output
<img width="1218" height="701" alt="image" src="https://github.com/user-attachments/assets/ac9eef74-ab41-4211-9523-039d5318b11d" />

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
