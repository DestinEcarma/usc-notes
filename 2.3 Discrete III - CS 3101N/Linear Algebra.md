---
creation date: 2024-08-23T20:36:50
tags:
  - Discrete
---

# Linear Algebra

> Linear algebra is a branch of mathematics that deals with linear equations and their representations in the vector space using matrices. In other words, ==linear algebra is the study of linear functions and vectors==. It is one of the most central topics of mathematics. Most modern geometrical concepts are based on linear algebra.
> 
> Linear algebra facilitates the modeling of many natural phenomena and hence, is an integral part of engineering and physics. Linear equations, matrices, and vector spaces are the most important components of this subject. In this article, we will learn more about linear algebra and the various associated topics.
> 
> -- <cite>Cuemath, n.d.</cite>

When information related to linear functions is presented in an organized form then it results in a matrix. Thus, linear algebra is concerned with vector spaces, vectors, linear functions, the system of linear equations, and matrices.

$$
\begin{pmatrix}
  a_{11} & a_{12} & a_{13} & \cdots & a_{1n} \\
  a_{21} & a_{22} & a_{23} & \cdots & a_{2n} \\
  \vdots & \vdots & \vdots & \ddots & \vdots \\
  a_{m1} & a_{m2} & a_{m3} & \cdots & a_{mn}
\end{pmatrix}

\left\{\begin{matrix}
	a_11x_1 + a_12x_2 + a_13x_3 + \cdots + a_1nx_n = c_1 \\
	a_21x_1 + a_22x_2 + a_23x_3 + \cdots + a_2nx_n = c_2 \\
	\vdots \\
	a_m1x_1 + a_m2x_2 + a_m3x_3 + \cdots + a_mnx_n = c_m
\end{matrix}\right.
$$

Using and interpreting data requires storing and manipulating sets of numbers in conceptually and computationally helpful ways. The language of linear algebra provides basic vocabulary, visualizations, and mathematical results for understanding the structure of a dataset (Mathigon, n.d.).

## What is Linear Algebra?

> Linear algebra can be defined as a branch of mathematics that deals with the study of linear functions in vector spaces. When information related to linear functions is presented in an organized form then it results in a matrix. Thus, linear algebra is concerned with vector spaces, vectors, linear functions, the system of linear equations, and matrices. These concepts are a prerequisite for sister topics such as geometry and functional analysis.
> 
> -- <cite>Cuemath, n.d.</cite>

Linear algebra is considered a basic concept in the modern presentation of geometry. It is mostly used in Physics and Engineering as ==it helps to define the basic objects such as planes, lines and rotations of the object==. It allows us to model many natural phenomena, and also it has a computing efficiency.

$$
\left\{\begin{matrix}
    2x + 2y & = 2 \\
    x - 2y & = 4
\end{matrix}\right.
$$

$$
\begin{pmatrix}
    2 & 2 \\
    1 & -2
\end{pmatrix}
\begin{pmatrix}
    x \\
    y
\end{pmatrix} = \begin{pmatrix}
    2 \\
    4
\end{pmatrix}
$$

$$
\begin{pmatrix}
    2 & 2 \\
    1 & -2
\end{pmatrix}
\begin{pmatrix}
    2 \\
    -1
\end{pmatrix} = \begin{pmatrix}
    2 \\
    4
\end{pmatrix}
$$

$$
2\begin{pmatrix}
    2 \\
    1
\end{pmatrix} + (-1) \begin{pmatrix}
    2 \\
    -2
\end{pmatrix} = \begin{pmatrix}
    2 \\
    4
\end{pmatrix}
$$

![[Figure 1.excalidraw|center]]

**Recall:** The equation of a line in two-dimensional space has the form $a_{1}x + a_{2}y = b$ where $a_{1}$, $a_{2}$, $b$ are constants. this is a **linear equation in tow variables** $x$ and $y$. Similarly, the equation of a plane in three-dimensional space has the form $a_{1}x + a_{2}y + a_{3}z = b$ where $a_{1}$, $a_{2}$, $a_{3}$ and $b$ are constants. This is a **linear equation in three variables** $x$, $y$ and $z$.

- Real number $(\mathbb{R})$ is a 1-dimentional space.
- $\mathbb{R}^{2} = \mathbb{R} \times \mathbb{R}$ is a 2-dimentional space.
- $\mathbb{R}^{3} = \mathbb{R} \times \mathbb{R} \times \mathbb{R}$ is a 3-dimentional space.

## References

1. Cuemath. (n.d.). Linear Algebra - Definition, Topics, Formulas, Examples. Cuemath. Retrieved August 23, 2024, from https://www.cuemath.com/algebra/linear-algebra/
2. Mathigon. (n.d.). Linear Algebra – Mathigon. Retrieved August 23, 2024, from https://mathigon.org/course/linear-algebra