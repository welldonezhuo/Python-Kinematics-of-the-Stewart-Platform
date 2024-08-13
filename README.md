# Kinematics-of-the-Stewart-Platform ⚙️

## Description 👀
Welcome to the Planar Stewart Platform Project repository. 

This project models a simplified two-dimensional version of the Stewart platform, a manipulator composed of a triangular platform controlled by three variable-length struts. The primary goal is to solve the forward kinematics problem, determining the platform's position and orientation given the lengths of the three struts.

## Project Overview 🙌
A Stewart platform typically consists of six variable-length struts supporting a payload, providing six degrees of freedom. This project simplifies the concept to two dimensions, modeling the platform as a triangle controlled by three struts. The inner triangle's dimensions are defined by the lengths $L_1, L_2,$ and $L_3,$ with $\gamma$ denoting the angle across from side $L_1$. The strut lengths are represented by $p_1$, $p_2$, and $p_3$.

The forward kinematics problem involves computing the position $(x, y)$ and orientation $\theta$ of the platform for given strut lengths $p_1$, $p_2$, and $p_3$. While no closed-form solution exists, this project uses trigonometric equations and numerical methods to solve the problem.

## Equations 🧮
The following equations describe the relationship between the platform's position and the strut lengths:

$p_1^2 = x^2 + y^2$
p_2^2 = (x + A_2)^2 + (y + B_2)^2$
p_3^2 = (x + A_3)^2 + (y + B_3)^2$

where:

A_2 &= L_2 \cos \theta + x_1 
B_2 &= L_3 \sin \theta 
A_3 &= L_2 \cos (\theta + \gamma) - x_2 = L_2 [ \cos (\theta) \cos (\gamma) - \sin (\theta) \sin (\gamma) ] - x_2
B_3 &= L_2 \sin (\theta + \gamma) - y_2 = L_2 [ \cos (\theta) \sin (\gamma) + \sin (\theta) \cos (\gamma) ] - y_2


These equations are solved to find the values of \(x\) and \(y\) in terms of \( \theta \):

x &= \frac{N_1}{D} = \frac{B_3 (p_2^2 - p_1^2 - A_2^2 - B_2^2) - B_2 (p_3^2 - p_1^2 - A_3^2 - B_3^2)}{2 (A_2 B_3 - B_2 A_3)} \\
y &= \frac{N_2}{D} = \frac{-A_3 (p_2^2 - p_1^2 - A_2^2 - B_2^2) + A_2 (p_3^2 - p_1^2 - A_3^2 - B_3^2)}{2 (A_2 B_3 - B_2 A_3)}
\end{aligned}


## Implementation 👩‍💻
This repository includes a Jupyter Notebook that walks through the derivation of the necessary equations and demonstrates how to solve them using numerical methods. The notebook is well-commented to guide you through the process.

## Reference 📘
This is a reality check problem from Numerical Analysis 3rd edition by Sauer
