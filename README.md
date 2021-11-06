import numpy as np
from mpl_toolkits import mplot3d
import matplotlib.pyplot as plt
import matplotlib.pyplot as plt
from sympy import *
import math


owo = input("Enter 'a)' for x/y in terms of z \n..... 'b)' for z in terms of x/y:::")

if owo == 'a)':
    z = Symbol('z')
    ex = eval(input("Enter equation in z for x:"))
    exx = eval(input("Enter equation in z for y:"))
    ex = lambdify(z, ex)
    exx = lambdify(z, exx)


    def X():
        return np.float64(ex(zz))


    def Y():
        return np.float64(exx(zz))


    zz = np.linspace(-20, 20, 50)


    ax = plt.axes(projection='3d')
    ax.plot3D(ex(zz), exx(zz), zz)
    ax.set_xlabel('x')
    ax.set_ylabel('y')
    ax.set_zlabel('z')

    plt.show()

if owo == 'b)':
    x = Symbol('x')
    y = Symbol('y')
    eq = eval(input("Enter basic equation in x/y for z:"))
    eq = lambdify([x, y], eq)


    def f(xx, yy):
        return eq(xx, yy)


    xx = np.linspace(-20, 20, 50)
    yy = np.linspace(-20, 20, 50)

    X, Y = np.meshgrid(xx, yy)
    Z = f(X, Y)

    ax = plt.axes(projection='3d')
    ax.contour3D(X, Y, Z, 50, cmap='viridis')
    ax.set_xlabel('x')
    ax.set_ylabel('y')
    ax.set_zlabel('z')

    plt.show()

