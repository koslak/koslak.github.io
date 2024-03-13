---
title: Linear Algebra - Row Reduction
date: 2024-03-05 10:00:00 -0500
categories: [Machine Learning, Math]
math: true
---

### Row Reduction
The process of applying elementary row operations to simplify a matrix is called row reduction.

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
