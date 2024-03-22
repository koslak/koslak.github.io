---
title: Linear Algebra - Matrix
date: 2024-03-05 10:00:00 -0500
categories: [Machine Learning, Math]
math: true
---

### Matrix Multiplication
Multiplication of matrices is only possible for cases like this:

$$
 A(m \times n) \cdot B(n \times p) = C(m \times p)
 \\
$$

That is, a matrix $$A$$ of size $$m \times n$$, and a matrix $$B$$ of size $$n \times p$$ 
has the same number of columns ($$n$$) for A and the same number of rows for B ($$n$$).

The multiplication of $$A$$ and $$B$$ is a matrix $$C (m \times p)$$ in which:

$$
 c_{ij} = (\text{row } i \text{ of } A) \cdot (\text{column } j \text{ of } B)
$$

#### Example:

$$
C = \left[\begin{array}{cc}
   1 & 3  \\
  -2 & 4 \\
\end{array}\right]
\left[\begin{array}{cc}
   3 & -2  \\
   5 & 6 \\
\end{array}\right]
$$

$$
\begin{align}
    c_{11} &= [1, 3]
      \left[\begin{array}{c}
         3 \\
         5 \\
      \end{array}\right] = (1)(3) + (3)(5) = 18\\

    c_{12} &= [1, 3]
      \left[\begin{array}{c}
         -2 \\
         6 \\
      \end{array}\right] = (1)(-2) + (3)(6) = 16\\

    c_{21} &= [-2, 4]
      \left[\begin{array}{c}
         3 \\
         5 \\
      \end{array}\right] = (-2)(3) + (4)(5) = 14\\

    c_{22} &= [-2, 4]
      \left[\begin{array}{c}
         -2 \\
         6 \\
      \end{array}\right] = (-2)(-2) + (4)(6) = 28
\end{align}
$$

$$
C = A \times B = 
      \left[\begin{array}{cc}
         18 & 16 \\
         14 & 28 \\
      \end{array}\right] 
$$

Another way of seeing this is:

$$
C = \left[\begin{array}{cc}
   1 & 3  \\
  -2 & 4 \\
\end{array}\right]
\left[\begin{array}{cc}
   3 & -2  \\
   5 & 6 \\
\end{array}\right] = 
\left[\begin{array}{cc}
   (1)(3) + (3)(5) & (1)(-2) + (3)(6)  \\
  (-2)(3) + (4)(5) & (-2)(-2) + (4)(6) \\
\end{array}\right]
=
\left[\begin{array}{cc}
   3 + 15 & -2 + 18  \\
  -6 + 20 & 4 + 24 \\
\end{array}\right] 
$$
$$
\\
\\
C =
\left[\begin{array}{cc}
   18 & 16 \\
   14 & 28 \\
\end{array}\right] 
$$

### Cofactor

Let $$A$$ be an $$n \times\ n$$ matrix. The $$ijth$$ cofactor of $$A$$, denoted $$A_{ij}$$, is given by

$$
A_{ij} = (-1)^{i+j}\times|M_{ij}|
$$

#### Example

Calculate $$A_{32}$$ for the following matrix:

$$
A = \left[\begin{array}{cccc}
   1 & -3 & 5 & 6  \\
   2 & 4 & 0 & 3  \\
   1 & 5 & 9 & -2  \\
   4 & 0 & 2 & 7  \\
\end{array}\right] \\
\\
$$

The formula says:

$$
A_{32} = (-1)^{3+2}\times|M_{32}| 
$$

This means we need to calculate 
$$
|M_{32}|
$$
:

$$
\\
|M_{32}| = \begin{vmatrix}
   1 & 5 & 6  \\
   2 & 0 & 3  \\
   4 & 2 & 7  \\
\end{vmatrix} = 8
$$



$$
A_{32} = (-1)^{3+2}\times|M_{32}| = (-1)^5\times8 \\
$$

$$
A_{32} = -8
$$

### Adjugate matrix (or adjoint of a matrix)

The adjoint of a square matrix $$A$$ is the transpose of its cofactor matrix.

#### Example:

For the following matrix:
$$
A = \left[\begin{array}{ccc}
   2 & 4 & 3  \\
   0 & 1 & -1  \\
   3 & 5 & 7  \\
\end{array}\right] \\
$$

Calculate $$adj A$$. First we calculate the cofactor matrix:

$$
A = \left[\begin{array}{ccc}
   A_{11} & A_{12} & A_{13}  \\
   A_{21} & A_{22} & A_{23}  \\
   A_{31} & A_{32} & A_{33}  \\
\end{array}\right] \\
$$

$$
\\
|A_{11}| = \begin{vmatrix}
   1 & -1 \\
   5 & 7 \\
\end{vmatrix} = 12

\qquad|A_{12}| = - \begin{vmatrix}
   0 & -1 \\
   3 & 7 \\
\end{vmatrix} = -3

\qquad|A_{13}| = \begin{vmatrix}
   0 & 1 \\
   3 & 5 \\
\end{vmatrix} = -3

$$

$$

|A_{21}| = -\begin{vmatrix}
   4 & 3 \\
   5 & 7 \\
\end{vmatrix} = -13

\qquad|A_{22}| = \begin{vmatrix}
   2 & 3 \\
   3 & 7 \\
\end{vmatrix} = 5

\qquad|A_{23}| = - \begin{vmatrix}
   2 & 4 \\
   3 & 5 \\
\end{vmatrix} = 2

$$

$$

|A_{31}| = \begin{vmatrix}
   4 & 3 \\
   1 & -1 \\
\end{vmatrix} = -7

\qquad|A_{32}| = - \begin{vmatrix}
   2 & 3 \\
   0 & -1 \\
\end{vmatrix} = 2

\qquad|A_{33}| = \begin{vmatrix}
   2 & 4 \\
   0 & 1 \\
\end{vmatrix} = 2
$$

With these values we calculate $$adj A$$:

$$
adj A = \left[\begin{array}{ccc}
   A_{11} & A_{21} & A_{31}  \\
   A_{12} & A_{22} & A_{32}  \\
   A_{13} & A_{23} & A_{33}  \\
\end{array}\right] =

\left[\begin{array}{ccc}
   12 &  -13 & -7  \\
   -3 & 5  & 2  \\
   -3 & 2 & 2  \\
\end{array}\right]
$$

### Inverse of a Matrix

$$
A^{-1} = \frac{1}{det A} \cdot adj A
$$

#### Example

For the following matrix:
$$
A = \left[\begin{array}{ccc}
   2 & 4 & 3  \\
   0 & 1 & -1  \\
   3 & 5 & 7  \\
\end{array}\right] \\
$$

Determine whether $$A$$ is invertible and calculate $$A^-1$$ if exists.

$$det A = 3 \neq 0$$

This means $$A$$ is invertible. From the previous section, we now $$adj A$$:

$$
adj A = \left[\begin{array}{ccc}
   12 &  -13 & -7  \\
   -3 & 5  & 2  \\
   -3 & 2 & 2  \\
\end{array}\right]
$$

This means:

$$
A^{-1} = \frac{1}{3}\times
\left[\begin{array}{ccc}
   12 &  -13 & -7  \\
   -3 & 5  & 2  \\
   -3 & 2 & 2  \\
\end{array}\right] =
\left[\begin{array}{ccc}
   4 &  \frac{-13}{3} & \frac{-7}{3}  \\
   -1 & \frac{5}{3}  & \frac{2}{3}  \\
   -1 & \frac{2}{3} & \frac{2}{3} \\
\end{array}\right]
$$