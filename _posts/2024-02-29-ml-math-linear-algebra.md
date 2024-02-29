---
title: Linear Algebra - Equation & Matrix
date: 2023-10-01 10:00:00 -0500
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
        R_2 \to 2 * R_1
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

> A system that has a linear `dependence` is a `singular` system.
A system that has a linear `independence` is a `non-singular` system.
{: .prompt-info }

Calculating the linear dependency of a system can be complex, but there is an easier way using the concept of `Determinant`.













