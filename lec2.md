# LEC 2: Elimination with Matricies

- Elimination -> Success or Failure  
- Back-Substitution  
- Elimination Matricies  
- Matrix Multiplication  

### Elimination

\begin{align}
1x + 2y + z &= 2 \\
3x + 8y + z &= 12 \\
0x + 4y + z &= 2
\end{align}

Start with the first **pivot**, the goal is to multiply the number and subtract from the below number(s) to turn it/them into 0. Here we multiply by 3 and subtract. Row 3, Col 1 is ignored since it's already 0.

\begin{bmatrix}
\underline{1} & 2 & 1 \\
3 & 8 & 1 \\
0 & 4 & 1
\end{bmatrix}
\qquad
\begin{bmatrix}
2 \\
12 \\
2
\end{bmatrix}

Do the same with the second **pivot**.

\begin{bmatrix}
\underline{1} & 2 & 1 \\
0 & \underline{2} & -2 \\
0 & 4 & 1
\end{bmatrix}
\qquad
\begin{bmatrix}
2 \\
6 \\
2
\end{bmatrix}

And the third **pivot**.

\begin{bmatrix}
\underline{1} & 2 & 1 \\
0 & \underline{2} & -2 \\
0 & 0 & \underline{5}
\end{bmatrix}
\qquad
\begin{bmatrix}
2 \\
6 \\
10
\end{bmatrix}

- The above 3x3 matrix is known as U and the 3x1 vector is b
- Rows can be swapped to avoid zero pivots which are not allowed

From here it's possible to solve for x, y and z. This is known as **Back Substitution**.

$$
\begin{align}
1x + 2y + 1z &= 2 \\
0x + 2y - 2z &= 12 \\
0x + 0y + 5z &= 2
\end{align}
\qquad
\begin{align}
x = 2 \\
y = 1 \\
z = -2
\end{align}
$$

### Matrix Multiplication:

$$
\begin{bmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{bmatrix}
\qquad
\begin{bmatrix}
3 \\
4 \\
5
\end{bmatrix}
\qquad
=
\qquad
\begin{align}
3 x col1 \\
4 x col2 \\
5 x col3
\end{align}
$$

$$
\begin{bmatrix}
1 & 2 & 7
\end{bmatrix}
\qquad
\begin{bmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{bmatrix}
\qquad
=
\qquad
\begin{align}
+1 x row1 \\
+2 x row2 \\
+7 x row3
\end{align}
$$

### Elimination Matricies:

Subtract 3 x row1 from row 2.

$$
\begin{bmatrix}
1 & 0 & 0 \\
\underline{-3} & \underline{1} & \underline{0} \\
0 & 0 & 1
\end{bmatrix}
\qquad
\begin{bmatrix}
1 & 2 & \underline{1} \\
3 & 8 & \underline{1} \\
0 & 4 & \underline{1}
\end{bmatrix}
\qquad
=
\qquad
\begin{bmatrix}
1 & 2 & 1 \\
0 & 2 & \underline{-2} \\
0 & 4 & 1
\end{bmatrix}
$$

$$
\begin{bmatrix}
1 & 0 & 0 \\
-3 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
\qquad
=
\qquad
E_{21}
\qquad
->
\qquad
\begin{bmatrix}
1 & 2 & 1 \\
\underline{0} & 2 & -2 \\
0 & 4 & 1
\end{bmatrix}
$$

Step2 : subtract 2 x row2 from row 3.

$$
E_{32}
\qquad
->
\qquad
\begin{bmatrix}
1 & 0 & 0 \\
0 & 2 & -2 \\
0 & 0 & 5
\end{bmatrix}
\qquad
\begin{bmatrix}
1 & 2 & 1 \\
0 & 2 & \underline{-2} \\
0 & 4 & 1
\end{bmatrix}
\qquad
=
\qquad
\begin{bmatrix}
1 & 2 & 1 \\
0 & 2 & -2 \\
0 & 0 & 5
\end{bmatrix}
$$

### The entire problem in Matrix Notation

$$
E_{32}(E_{21}A) = U
$$

The order of the matricies cannot be changed but the order of multiplication can be.

$$
(E_{32}E_{21})A = U
$$

This is the Associative Law

### Permutation

Exchange rows 1 and 2.

$$
\begin{bmatrix}
0 & 1 \\
1 & 0
\end{bmatrix}
\qquad
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
\qquad
=
\qquad
\begin{bmatrix}
c & d \\
a & b
\end{bmatrix}
$$

$$
\begin{bmatrix}
0 & 1 \\
1 & 0
\end{bmatrix}
\qquad
=
\qquad
P
$$

What about exchanging columns?

$$
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
\qquad
\begin{bmatrix}
0 & 1 \\
1 & 0
\end{bmatrix}
\qquad
=
\qquad
\begin{bmatrix}
b & a \\
d & c
\end{bmatrix}
$$

Note the Commutative Law doesn't apply.

$$
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
\qquad
\begin{bmatrix}
0 & 1 \\
1 & 0
\end{bmatrix}
\qquad
\neq
\qquad
\begin{bmatrix}
0 & 1 \\
1 & 0
\end{bmatrix}
\qquad
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
$$

### Inverses

Think about how to get from U to A.

$$
\begin{bmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{bmatrix}
\qquad
\begin{bmatrix}
1 & 0 & 0 \\
-3 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
\qquad
=
\qquad
\begin{bmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
$$

$$
\begin{bmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{bmatrix}
\qquad
=
\qquad
\begin{bmatrix}
1 & 0 & 0 \\
3 & 1 & 0 \\
0 & 0 & 1
\end{bmatrix}
$$
