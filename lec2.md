# LEC 2: Elimination with Matricies

Elimination -> Success or Failure  
Back-Substitution  
Elimination Matricies  
Matrix Multiplication  

\begin{align}
1x + 2y + z &= 2 \\
3x + 8y + z &= 12 \\
0x + 4y + z &= 2
\end{align}

Start with the first pivot, the goal is to multiply the number and subtract from the below to turn it into a 0

Here we multiply by 3 and subtract

\begin{bmatrix}
\underline{1} & 2 & 1 \\
3 & 8 & 1 \\
0 & 4 & 1
\end{bmatrix}

Now we do the same with the second pivot

\begin{bmatrix}
\underline{1} & 2 & 1 \\
0 & \underline{2} & -2 \\
0 & 4 & 1
\end{bmatrix}

Now we have the third pivot

\begin{bmatrix}
\underline{1} & 2 & 1 \\
0 & \underline{2} & -2 \\
0 & 0 & \underline{5}
\end{bmatrix}

Rows can be swapped to avoid zero pivots which are not allowed

The b vector can be appended

\begin{bmatrix}
2 \\
12 \\
2
\end{bmatrix}

which becomes

\begin{bmatrix}
2 \\
6 \\
-10
\end{bmatrix}

From here it's possible to solve for x, y and z

\begin{align}
1x + 2y + 1z &= 2 \\
0x + 2y - 2z &= 12 \\
0x + 0y + 5z &= 2
\end{align}

z = -2
y = 1
x = 2

Matrix A * Matrix B is not the same as Matrix B * Matrix A
