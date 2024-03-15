---
title: Linear Algebra - Equations & Determinant
date: 2024-02-29 10:00:00 -0500
categories: [Machine Learning, Math]
math: true
---

## System of Sentences

$$
\text{Non-singular system (complete)}=\begin{cases}
    \text{A is black} \\
    \text{B is } \color{orange}\text{orange}\\
    \text{C is } \color{red}\text{red}\\
  \end{cases}
$$

$$
\text{Singular system (redundant)}=\begin{cases}
    \text{A is black} \\
    \text{A is black} \\
    \text{C is } \color{red}\text{red}\\
  \end{cases}
$$

$$
\text{Singular system (redundant)}=\begin{cases}
    \text{A is black} \\
    \text{A is black} \\
    \text{A is black} \\
  \end{cases}
$$

$$
\text{Singular system (contradictory)}=\begin{cases}
    \text{A is black} \\
    \text{A is grey} \\
    \text{C is } \color{red}\text{red}\\
  \end{cases}
$$

> In a nutshell, a `Non-singular` system is a system that carries as many pieces of information as sentences. 
So it's the most informative system can be, and a `Singular` system is less informative than a non-singular one.
{: .prompt-info }

## System of Equations

System 1 (Non-singular):

$$
\text{Unique solution (a = 8, b = 2), two lines crossing}=\begin{cases}
    {x + y = 10} \\
    {x + 2y = 12} 
  \end{cases}
$$

System 2 (Singular):

$$
\text{Infinite solutions (a = 8, 7, 6, b = 2, 3, 4), same line}=\begin{cases}
    {x + y = 10} \\
    {2x + 2y = 20} 
  \end{cases}
$$

System 3 (Singular):

$$
\text{No solution, parallel lines}=\begin{cases}
    {x + y = 10} \\
    {2x + 2y = 24} 
  \end{cases}
$$

## System of equations as a Matrix

A system of equations can be represented as a matrix:

$$
\begin{align*}
{10x + 3y = 2} \\
{3x + 13y = 4} 
\end{align*}

\Longrightarrow

\left[\begin{array}{cc|c}  
 10 & 3 & 2 \\  
 3 & 13 & 4  
\end{array}\right]
$$

A system of equations is set be `homogeneous` if all values on the right side are equal to cero: 

$$
\left[\begin{array}{cc|c}  
 2 & 6 & 0 \\  
 8 & 1 & 0  
\end{array}\right]
$$

## Linear Dependence and Independence

For a system of equations:

\begin{equation} \label{eq1} 
{x - y = 7}
\end{equation}

\begin{equation} \label{eq2} 
{2x - 2y = 14} 
\end{equation}

In order to determine its linear dependency, you need to first represent it as a matrix in an homogeneous form:

$$
\begin{align*}
{x - y = 7} \\
{2x - 2y = 14} 
\end{align*}

\Longrightarrow

\left[\begin{array}{cc|c}  
 1 & -1 & 7 \\  
 2 & -2 & 14  
\end{array}\right]
$$

$$
\text{Homogeneous Form}

\Longrightarrow

\left[ \begin{array}{cc|c}
       1 & -1 & 0 \\
       2 & -2 & 0 \\
     \end{array} \right]
     \begin{array}{l}
        R_1 \\
        R_2 
     \end{array}
$$

> The $R$ means `Row`. 
{: .prompt-info }

We say the rows are `linearly dependent` because the second row can be formed by a modification of the first row:

$$
\left[ \begin{array}{cc|c}
       1 & -1 & 0 \\
       2 & -2 & 0 \\
     \end{array} \right]
     \begin{array}{l}
        R_1 \\
        R_2 \to 2R_1
     \end{array}
$$

Another example:

$$
\begin{align*}
{x + z = 0} \\
{y = 0}  \\
{3x + 2y + 3z = 0} 
\end{align*}
$$

Represented in Matrix form:

$$
\left[ \begin{array}{ccc|c}
       1 & 0 & 1 & 0 \\
       0 & 1 & 0 & 0 \\
       3 & 2 & 3 & 0 \\
     \end{array} \right]
     \begin{array}{l}
        R_1 \\
        R_2 \\
        R_3 
     \end{array}
$$

The third row can be represented as a combination of the first two rows:

$$
\begin{align*}
{ R_3 \to 3R_1 + 2R_2}
\end{align*}
$$

> A system that has a linear `dependence` is a `singular` system. \\
A system that has a linear `independence` is a `non-singular` system.
{: .prompt-info }

Calculating the linear dependency of a system can be complex, but there is an easier way using the concept of `Determinant`.

## The Determinant

For the following matrix:

$$
\left[ \begin{array}{cc}
       a_{11} & a_{12} \\
       a_{21} & a_{22} \\
     \end{array} \right]
$$

The Determinant is defined as:

$$
det A = \begin{vmatrix} A \end{vmatrix} = a_{11}a_{22} - a_{12}a_{21}
$$

Example:

$$
\begin{vmatrix} A \end{vmatrix} = 
\begin{vmatrix} 
1 & 1 \\
1 & 2 \\
\end{vmatrix} = 
\text{= 1} \cdot\text{2} - \text{1}\cdot\text{1 = 1}
$$

For a 3x3 matrix, the determinant is calculated like this:

$$
A = \begin{bmatrix}
   a_{11} & a_{12} & a_{13} \\
   a_{21} & a_{22} & a_{23} \\
   a_{31} & a_{32} & a_{33}
\end{bmatrix}
$$

$$
\\
det A = |A| = a_{11}\begin{vmatrix}
   a_{22} & a_{23} \\
   a_{32} & a_{33}
\end{vmatrix} - 
a_{12}\begin{vmatrix}
   a_{21} & a_{23} \\
   a_{31} & a_{33}
\end{vmatrix} +
a_{13}\begin{vmatrix}
   a_{21} & a_{22} \\
   a_{31} & a_{32}
\end{vmatrix}
$$

Example:

$$
A = \begin{bmatrix}
   3 & 5 & 2 \\
   4 & 2 & 3 \\
   -1 & 2 & 4
\end{bmatrix}
$$

$$
\\
|A| = \begin{vmatrix}
   3 & 5 & 2 \\
   4 & 2 & 3 \\
   -1 & 2 & 4
\end{vmatrix} =
3\begin{vmatrix}
   2 & 3 \\
   2 & 4
\end{vmatrix} - 
5\begin{vmatrix}
   4 & 3 \\
   -1 & 4
\end{vmatrix} +
2\begin{vmatrix}
   4 & 2 \\
   -1 & 2
\end{vmatrix}
$$

$$
\\
|A| = 3 \cdot 2 - 5 \cdot 19 + 2 \cdot 10 = -69
$$

## Singularity based on the Determinant

$$
\text{System is}\begin{cases}
   \text{Non-singular} &\text{if detA} \neq {0} \\
   \text{Singular} &\text{if detA = 0}
\end{cases}
$$

Examples:

$$
A = \begin{bmatrix}
   1 & 1 \\
   1 & 2
\end{bmatrix}\to\text{|A| = 1} \cdot\text{2} - \text{1}\cdot\text{1 = 1}\to \color{#0000FF}\text{Non-singular}
$$

$$
\\
B=\begin{bmatrix}
   1 & 1 \\
   2 & 2
\end{bmatrix}\to\text{|B| = 1} \cdot\text{2} - \text{1}\cdot\text{2 = 0}\to \color{#0000FF}\text{Singular}
$$

> To summarize, the determinant of a matrix is `0` precisely when the matrix is `singular` and `non 0` when the matrix is `non-singular`.
{: .prompt-info }

## Triangular Matrix

A triangular matrix is a special kind of square matrix. A square matrix is called `lower triangular` if all the entries above the main diagonal are zero. 
Similarly, a square matrix is called `upper triangular` if all the entries below the main diagonal are zero.

$$
A = \begin{bmatrix}
   3 & 5 & 2 & 1 \\
   0 & 2 & 3 & 9 \\
   0 & 0 & 4 & 7 \\
   0 & 0 & 0 & 6 \\ 
\end{bmatrix}
$$

### Determinant of a Triangular Matrix

$$
det A = a_{11} \cdot a_{22} \cdot a_{33} \cdot\cdot\cdot a_{nn} 
$$

#### Example:

$$
\\
|A| = \begin{vmatrix}
   3 & 0 & 0 \\
   4 & 2 & 0 \\
   -1 & 2 & 4
\end{vmatrix} = 3 \cdot 2 \cdot 4 = 24
$$

## Determinant: Multiplication and Inverse of a Matrix

Two square matrices $$A$$ and $$B$$ then:

$$ det AB = det A \cdot det B $$

Also, if $$A$$ is invertible, then:

$$ det A^{-1} = \frac{1}{det A} $$

## Equation System and Unique Solution

Consider the following system of $$n$$ equations and $$n$$ variables:

$$
\begin{align*}
a_{11}x_{1} + a_{12}x_{2} + \cdot\cdot\cdot + a_{1n}x_{n} = b_1 \\
a_{21}x_{1} + a_{22}x_{2} + \cdot\cdot\cdot + a_{2n}x_{n} = b_2 \\
\cdot\cdot\cdot \\
a_{n1}x_{1} + a_{n2}x_{2} + \cdot\cdot\cdot + a_{nn}x_{n} = b_n \\
\end{align*}
$$

That can be written in the following form:

$$
A\mathbf{x} = \mathbf{b}
$$

Si $$det A \neq 0$$, then the system has a unique solution and it's given by:

$$\mathbf{x} = A^{-1}\mathbf{b}$$

> Si $$det A \neq 0$$, then the system has a unique solution 
{: .prompt-info }

#### Example:

$$
\begin{align*}
2x_1 + 4x_2 + 6x_3 = 18 \\
4x_1 + 5x_2 + 6x_3 = 24 \\
3x_1 + x_2 - 2x_3 = 4
\end{align*}
$$

Can be written as 

$$
A\mathbf{x} = \mathbf{b}
$$
 
with 

$$
A =  
\begin{bmatrix}
   2 & 4 & 6 \\
   4 & 5 & 6 \\
   3 & 1 & -2
\end{bmatrix},

\mathbf{x} =  
\begin{bmatrix}
   x_1 \\
   x_2 \\
   x_3
\end{bmatrix},

\mathbf{b} =  
\begin{bmatrix}
   18 \\
   24 \\
   4
\end{bmatrix}
$$

If we calculate $$det A$$ we got:

$$
\\
|A| = \begin{vmatrix}
   2 & 4 & 6 \\
   4 & 5 & 6 \\
   3 & 1 & -2
\end{vmatrix} = 6 \neq 0 
$$

which means this system has a unique solution.










