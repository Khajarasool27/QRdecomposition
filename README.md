# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
### Step 1: Start the process and input the matrix A.
### Step 2: Initialize matrix Q and u of appropriate sizes. Set the first column of u equal to the first column of A, and normalize to get the first column of Q.
### Step 3: For each subsequent column in A, compute the orthogonal projection onto the space spanned by the previous columns of Q and adjust the vector u accordingly. Normalize u to get the corresponding column of Q.
### Step 4: Construct the upper triangular matrix R using the dot product of A and the columns of Q.
### Step 5: Display the resulting Q and R matrices, then end the process.


## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: your name BOYALAKUNTLA KHAJA RASOOL
RegisterNumber: 212224230040
'''

import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print("The Q Matrix is \n",Q)
    print("The R Matrix is \n",R)
a = np.array(eval(input()))
QR_Decomposition(a)






```

## Output

![image](https://github.com/user-attachments/assets/f3b2fd07-f7e3-40ee-8b4c-888822f4250a)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
