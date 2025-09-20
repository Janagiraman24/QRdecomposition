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

### Program to QR decomposition using the Gram-Schmidt method
### Developed by: Janagiraman.M
### RegisterNumber: 212224230101
### Gram-Schmidt Method
```python
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
            u[:,i]-=(A[:,i]@Q[:,j]*Q[:,j])
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,n):
            R[i,j]=A[:,j]@Q[:,i]
    print("The Q Matrix is\n",Q)
    print("The R Matrix is\n",R)
a = np.array(eval(input()))
QR_Decomposition(a)

```

## Output

<img width="1206" height="620" alt="Screenshot 2025-09-20 093331" src="https://github.com/user-attachments/assets/5b389582-b7f3-42f0-9459-d769a29ed4ea" />
<img width="1196" height="495" alt="Screenshot 2025-09-20 093342" src="https://github.com/user-attachments/assets/8ad0c924-75b7-4d0b-9c85-c7abe6caf026" />


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
