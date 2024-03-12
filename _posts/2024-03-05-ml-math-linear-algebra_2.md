---
title: Linear Algebra - Row Reduction
date: 2024-03-05 10:00:00 -0500
categories: [Machine Learning, Math]
math: true
---

## Row Operations

1. Multiply or divide all entries in a row by a non-zer constant. 
1. Replace one row by the sum of itself and a multiple of another row.
3. Interchange two rows.

### Row Reduction
The process of applying elementary row operations to simplify a matrix is called row reduction.

### Echelon Form
The following matrices are in echelon form. The leading entries ($$\triangle$$) may have any nonzero value; 
the starred entries ($$*$$) may have any value (including zero).

$$
\left[ \begin{array}{ccc|c}
       \triangle & * & * & * \\
       0 & \triangle & * & * \\
       0 & 0 & 0 & 0 \\
     \end{array} \right]
     \begin{array}{l}
        R_1 \\
        R_2 \\
        R_3 
     \end{array}
$$

$$
\left[ \begin{array}{ccccc|c}
       0 & \triangle & * & * & * \\
       0 & 0 & 0 & \triangle & * \\
       0 & 0 & 0 & 0 & \triangle  \\
     \end{array} \right]
     \begin{array}{l}
        R_1 \\
        R_2 \\
        R_3 
     \end{array}
$$

> The places where there is a triangle, it's called a `pivot point`. The 
column where there is a pivot point is called a `pivot column`.
{: .prompt-info }

### Reduce Echelon Form
The following matrices are in reduced echelon form.

$$
\left[ \begin{array}{ccc|c}
       1 & * & * & * \\
       0 & 1 & * & * \\
       0 & 0 & 0 & 0 \\
     \end{array} \right]
     \begin{array}{l}
        R_1 \\
        R_2 \\
        R_3 
     \end{array}
$$

$$
\left[ \begin{array}{ccccc|c}
       0 & 1 & * & * & * \\
       0 & 0 & 0 & 1 & * \\
       0 & 0 & 0 & 0 & 1  \\
     \end{array} \right]
     \begin{array}{l}
        R_1 \\
        R_2 \\
        R_3 
     \end{array}
$$

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






