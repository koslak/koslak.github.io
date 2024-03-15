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

#### Row Operations

1. Multiply or divide all entries in a row by a non-zero constant. 
1. Replace one row by the sum of itself and a multiple of another row.
3. Interchange two rows.


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

### Reduced Echelon Form
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
