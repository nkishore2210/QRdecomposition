# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u

2.	The vector u and e is given by
	![image](https://github.com/nkishore2210/QRdecomposition/assets/118707090/40669b13-110e-4af5-9b9a-f1df65fa5a2a)

3.	Obtain the Q matrix   
    ![image](https://github.com/nkishore2210/QRdecomposition/assets/118707090/1bfd2874-1cf9-4287-b12d-342dc5ea6a5d)

4.	Construct the upper triangular matrix R
    ![image](https://github.com/nkishore2210/QRdecomposition/assets/118707090/aff17903-2393-4512-aa06-61cf748fb402)

## Program:
### Gram-Schmidt Method
```
#Program to QR decomposition using the Gram-Schmidt method
#Developed by: N.Kishore
#RegisterNumber: 212222240049

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
            u[:,i]-=(A[:,i] @ Q[:,j])*Q[:,j]
            Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j] @ Q[:,i]
    print(Q)
    print(R)
a=np.array(eval(input()))
QR_Decomposition(a)
```

## Output:

![Screenshot 2023-06-04 145344](https://github.com/nkishore2210/QRdecomposition/assets/118707090/807c7c82-f5cf-4110-acc3-9b203444a8be)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
