# Quick Notes

Linear algebra is a branch of mathematics concerning with linear equations, linear maps, and their representations in vector spaces and through matrices.

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

When information related to linear functions is presented in an organized form then it results in a matrix. Thus, linear algebra is concerned with vector spaces, vectors, linear functions, the system of linear equations, and matrices.

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

Linear algebra is considered a basic concept in the modern presentation of geometry. It is mostly used in Physics and Engineering as it helps to define the basic objects such as planes, lines and rotations of the object. It allows us to model many natural phenomena, and also it has a computing efficiency.

**Recall:** The equation of a line in two-dimensional space has the form $a_{1}x + a_{2}y = b$ where $a_{1}$, $a_{2}$, $b$ are constants. this is a **linear equation in tow variables** $x$ and $y$. Similarly, the equation of a plane in three-dimensional space has the form $a_{1}x + a_{2}y + a_{3}z = b$ where $a_{1}$, $a_{2}$, $a_{3}$ and $b$ are constants. This is a **linear equation in three variables** $x$, $y$ and $z$.

**Question: In graphing a line (or plane), where do you expect to find the solutions of the line (or plane)?**

**Answer:** The solutions of a line (or plane) are found on the line (or plane).

- Real number $(\mathbb{R})$ is a 1-dimentional space.
- $\mathbb{R}^{2} = \mathbb{R} \times \mathbb{R}$ is a 2-dimentional space.
- $\mathbb{R}^{3} = \mathbb{R} \times \mathbb{R} \times \mathbb{R}$ is a 3-dimentional space.

## Overview of Topics

- **Systems of Linear Equations**
- **Matrices**
- **Determinants**
- **Vector Spaces**
- **Inner Product Spaces**
- **Eigenvalues and Eigenvectors**

## References

1. Admin. (2023, January 10). Linear Algebra Introduction | Linear Functions, Applications and Examples. BYJUS. https://byjus.com/maths/linear-algebra/
2. Banerjee, S., & Roy, A. (2014). Linear Algebra and Matrix Analysis for Statistics. CRC Press.
3. Mathigon. (n.d.). Linear Transformations – Linear Algebra – Mathigon. Mathigon. Retrieved August 20, 2024, from https://mathigon.org/course/linear-algebra/linear-transformations
4. Project, X. (n.d.). VEC-0040: Linear Combinations of Vectors. Ximera. https://ximera.osu.edu/la/LinearAlgebra/VEC-M-0040/main
5. Ronan, M. A. (2024, August 16). Linear algebra | Matrices, Vectors & Equations. Encyclopedia Britannica. https://www.britannica.com/science/linear-algebra
6. Strang, G. (2006). Linear algebra and its applications. Recording for the Blind & Dyslexic.
7. Weisstein, W. (n.d.). Linear Algebra. MathWorld. Retrieved August 20, 2024, from https://mathworld.wolfram.com/LinearAlgebra.html
---

Linear algebra is a branch of mathematics that is widely used throughout science and engineering. It is used to solve systems of linear equations, to study the properties of matrices, and to analyze the geometry of objects in space. Linear algebra is also used in computer graphics, computer vision, and machine learning.

Linear algebra is obviously a algebra, but it is different from the algebra that you learned in high school. In high school algebra, you learned how to solve equations with variables, such as $x + 3 = 5$. In linear algebra, you work with vectors and matrices, which are collections of numbers.

In this article, we will introduce some of the basic concepts of linear algebra, including vectors, matrices, and systems of linear equations. We will also discuss some of the applications of linear algebra in science and engineering.

Learning the fundamentals of linear algebra is essential for anyone who wants to work in a field that uses mathematics. Whether you are studying physics, engineering, computer science, or any other field, you will likely encounter linear algebra at some point in your studies.

## Vectors

A vector is a mathematical object that has both magnitude and direction. Vectors are used to represent quantities that have both size and direction, such as velocity, force, and displacement. In linear algebra, vectors are represented as arrays of numbers.

## Matrices

A matrix is a rectangular array of numbers. Matrices are used to represent linear transformations, such as rotations, reflections, and scaling. Matrices are also used to solve systems of linear equations.
