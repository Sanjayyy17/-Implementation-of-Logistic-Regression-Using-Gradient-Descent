# Implementation-of-Logistic-Regression-Using-Gradient-Descent

## AIM:
To write a program to implement the the Logistic Regression Using Gradient Descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the libraries and Load the dataset.

2.Define X and Y array and Define a function for costFunction,cost and gradient.

3.Define a function to plot the decision boundary.

4.Define a function to predict the Regression value. 


## Program:
```
/*
Program to implement the the Logistic Regression Using Gradient Descent.
Developed by:gokul sachik.k 
RegisterNumber:  212223220025


import numpy as np
import matplotlib.pyplot as plt
from scipy import optimize

data=np.loadtxt("ex2data1.txt",delimiter=',')
X=data[:,[0,1]]
y=data[:,2]

X[:5]

y[:5]

plt.figure()
plt.scatter(X[y==1][:,0],X[y==1][:,1],label="Admitted")
plt.scatter(X[y==0][:,0],X[y==0][:,1],label="Not Admitted")
plt.xlabel("Exam 1 score")
plt.ylabel("Exam 2 score")
plt.legend()
plt.show()

def sigmoid(z):
    return 1/(1+np.exp(-z))

plt.plot()
X_plot=np.linspace(-10,10,100)
plt.plot(X_plot,sigmoid(X_plot))
plt.show()

def costFunction (theta,X,y):
    h=sigmoid(np.dot(X,theta))
    J=-(np.dot(y,np.log(h))+np.dot(1-y,np.log(1-h)))/X.shape[0]
    grad=np.dot(X.T,h-y)/X.shape[0]
    return J,grad

X_train=np.hstack((np.ones((X.shape[0],1)),X))
theta=np.array([0,0,0])
J,grad=costFunction(theta,X_train,y)
print(J)
print(grad)

X_train=np.hstack((np.ones((X.shape[0],1)),X))
theta=np.array([-24,0.2,0.2])
J,grad=costFunction(theta,X_train,y)
print(J)
print(grad)

def cost (theta,X,y):
    h=sigmoid(np.dot(X,theta))
    J=-(np.dot(y,np.log(h))+np.dot(1-y,np.log(1-h)))/X.shape[0]
    return J

def gradient (theta,X,y):
    h=sigmoid(np.dot(X,theta))
    grad=np.dot(X.T,h-y)/X.shape[0]
    return grad

X_train=np.hstack((np.ones((X.shape[0],1)),X))
theta=np.array([0,0,0])
res=optimize.minimize(fun=cost,x0=theta,args=(X_train,y),method='Newton-CG',jac=gradient)
print(res.fun)
print(res.x)

def plotDecisionBoundary(theta,X,y):
    x_min,x_max=X[:,0].min()-1,X[:,0].max()+1
    y_min,y_max=X[:,1].min()-1,X[:,1].max()+1
    xx,yy=np.meshgrid(np.arange(x_min,x_max,0.1),np.arange(y_min,y_max,0.1))
    X_plot=np.c_[xx.ravel(),yy.ravel()]
    X_plot=np.hstack((np.ones((X_plot.shape[0],1)),X_plot))
    y_plot=np.dot(X_plot,theta).reshape(xx.shape)
    
    plt.figure()
    plt.scatter(X[y==1][:,0],X[y==1][:,1],label="Admitted")
    plt.scatter(X[y==0][:,0],X[y==0][:,1],label="Not Admitted")
    plt.contour(xx,yy,y_plot,levels=[0])
    plt.xlabel("Exam 1 score")
    plt.ylabel("Exam 2 score")
    plt.legend()
    plt.show()


plotDecisionBoundary(res.x,X,y)

prob=sigmoid(np.dot(np.array([1,45,85]),res.x))
print(prob)

def predict(theta,X):
    X_train =np.hstack((np.ones((X.shape[0],1)),X))
    prob=sigmoid(np.dot(X_train,theta))
    return (prob>=0.5).astype(int)
np.mean(predict(res.x,X)==y)
```

## Output:
## Array value of x:
![image](https://github.com/vksachin2018/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/149366019/177f4049-d300-460b-98d0-9c98f2b2bc62)


## Array value of y:
![image](https://github.com/vksachin2018/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/149366019/e24fb81d-81c8-4c87-b87e-dd4018b42a2d)

## score graph:
![270424409-edc4acfc-30af-40ec-9c5e-eac35cb89e19](https://github.com/vksachin2018/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/149366019/c4260b20-35c0-4029-8da2-06ee585aa2a8)

## sigmoid function graph:
![270424445-9bd4bfca-0274-4d02-97ea-88bc4274d31a](https://github.com/vksachin2018/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/149366019/a5cbc1a2-c7bb-4126-ae4b-38afd652ff61)

## x train grad value:
![image](https://github.com/vksachin2018/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/149366019/a2dc9a41-7932-45d7-9de6-a22c48ce33ad)

## y train grad value:
![image](https://github.com/vksachin2018/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/149366019/47b5d4fb-ae69-4eb2-bc12-aa94d3e9e276)

## Print res.x:
![image](https://github.com/vksachin2018/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/149366019/4370496e-5366-48bd-b54d-30ea40bd15fb)

## decision boundary graph:
![image](https://github.com/vksachin2018/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/149366019/4285624b-45fc-4589-a45e-0f34630ae56d)

## Probablity value:
![image](https://github.com/vksachin2018/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/149366019/9baedff3-ef3e-4994-adef-5ddc4a9edada)


## Prediction value of mean:
![270424764-1d6e9ca6-3ecf-4029-828b-1993ca653c66](https://github.com/vksachin2018/-Implementation-of-Logistic-Regression-Using-Gradient-Descent/assets/149366019/33355f99-f18f-4038-bcde-f932c3aeedd2)




## Result:
Thus the program to implement the the Logistic Regression Using Gradient Descent is written and verified using python programming.

