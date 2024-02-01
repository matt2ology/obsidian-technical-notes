---
aliases:
note-type: permanent
date-created: 2024-01-31
long-form-date-created: Wednesday, January 31, 2024
week-created: Week 05.3
time-created: 05:08 PM
---

# MATH 100 HW 01

Related : [1.1 Systems of Linear Equations](1.1%20Systems%20of%20Linear%20Equations.md)

## 1. (1 point) Solve the following system

> [!info] Solve the following system
>
> $$
> \huge
> {\begin{align*}
> -4x+8y&=0\\
> 12x+3y&=-54
> \end{align*}}
> $$

### 1. Strategy: Row Reduction

> [!info] System
>
> $$
> {\begin{align*}
> -4x+8y&=0\\
> 12x+3y&=-54
> \end{align*}}
> $$

**Step 1)** Rewrite in matrix form

$$
\large
\begin{align*}
    &\begin{matrix}&x&y&=\quad\end{matrix} \\
    &\left[
        \begin{array}{cc|c}
            -4&8&0 \\
            12&3&-54 \\
        \end{array}
    \right]
\end{align*}
$$

**Step 2)** Find the, pivot column, left-most non-zero colum

$$
\large
\begin{align*}
\text{[Pivot Column]}\\
    \left[\begin{array}{cc|c}
            \left[-4\right]&8&0 \\
            \left[12\right]&3&-54 \\
        \end{array}
    \right]
\end{align*}
$$

**Step 3)** Choose a non-zero entry in the pivot column - this will be called
the `pivot`

$$
\large
\left[\begin{array}{cc|c}
        \left(-4\right)&8&0 \\
        12&3&-54 \\
    \end{array}
\right]
$$

**Step 4)** Use replacement operations to create zeros _below_ the `pivot`

Multiply `row 1` by 3 and add `row 1` with `row 2`; then, replace `row 2` with
that sum

$$
\Large
\begin{align*}
    \left[\begin{array}{cc|c}
            \left(-4\right)&8&0 \\
            12&3&-54 \\
        \end{array}
    \right]
    {\Large\underset{3r_1\:+\:r_2\rightarrow\:r_2}{\sim}}
    \left[\begin{array}{cc|c}
            \left(-4\right)&8&0 \\
            0&\left(27\right)&-54 \\
        \end{array}
    \right]
\end{align*}
$$

> [!tip] Replacement operation
> **Replacement**: Replace a row by itself plus any multiple of another row
> $\large r_i+cr_j\rightarrow r_i$

**Step 5)** Cover-up (or ignore) the row containing the `pivot`, and repeat
steps 2-4 on the smaller matrix below. Continue repeating until there are no
more non-zero rows to modify.

Replace `row 2` by a scaled-down `row 2` by $\large \frac{1}{27}r_2$

$$
\Large
\begin{align*}
    \left[\begin{array}{cc|c}
            \left(-4\right)&8&0 \\
            0&\left(27\right)&-54 \\
        \end{array}
    \right]
    {\Large\underset{\frac{1}{27}r_2\:\rightarrow\:r_2}{\sim}}
    \left[\begin{array}{cc|c}
            \left(-4\right)&8&0 \\
            0&\left(1\right)&-2 \\
        \end{array}
    \right]
\end{align*}
$$

> [!tip] Scaling operation
> **Scaling**: Multiply any row by a non-zero number
> $\large cr_i\rightarrow r_i$

**Step 6)** Finish by solving the equations in standard form

**Equation 2**: $y=-2$

**Equation 1**:

$$
\begin{align*}
    -4x\:+\:8y\:&=0\\
    -4x\:+\:8\left(-2\right)\:&=0\qquad\text{Equation 2: $y=-2$}\\
    -4x\:-\:16\:&=0\qquad\text{Add 16 from both sides}\\
    -4x\:&=16\qquad\text{Divide 4 from both sides}\\
    \rightarrow\:x\:&=\:\frac{16}{-4}\qquad\text{Simplify}\\
    \rightarrow\:x\:&=\:-4
\end{align*}
$$

> [!done]
> So, the solution to the system is $x=-4$ and $y=-2$

### 1. The Naive - Substitution Method

> [!info] System
>
> $$
> {\begin{align*}
> -4x+8y&=0\\
> 12x+3y&=-54
> \end{align*}}
> $$

Subtract $12x$ from both sides

$$
{
\begin{align*}
12x + 3y &= -54 \\
-12x &\quad -12x\\
\hline
3y &= -54 - 12x \\
\end{align*}
}
$$

Divide both sides by 3

$$
{
\begin{align*}
3y &= -54 - 12x \\
\div 3 & \quad \div 3\\
\hline
y &= -18 - 4x
\end{align*}
}
$$

Substitute $y=-4x-18$ into equation $-4x + 8y = 0$

$$
\begin{align*}
-4x + 8y &= 0 \quad\text{Starting with the given equation} \\
-4x + 8(-4x - 18) &= 0 \quad\text{Now, substitute $y=−4x−18$}\\
-4x - 32x - 144 &= 0 \quad\text{Distribute the 8}\\
-36x - 144 &= 0 \quad\text{Combine like terms}\\
-36x &= 144 \quad\text{Now, add 144 to both sides to isolate the term with x}\\
x &= -4 \quad\text{Finally, divide both sides by -36 to solve for x}\\
\end{align*}
$$

Now, substitute $x=−4$ back into the equation $y=−4x−18$

$$
\begin{align*}
y &= -4(-4) - 18 \\
y &= 16 - 18 \\
y &= -2 \\
\end{align*}
$$

> [!done]
>
> So, the solution to the system is $x=-4$ and $y=-2$

## 2. (1 point) Solve the following system

> [!info] Solve the following system
>
> $$
> \huge
> {\begin{align*}
> 5x-8y&=-23 \\
> -4x-6y&=6
> \end{align*}}
> $$

### 2. Strategy: Row Reduction

Given the system of equations:

$$
\begin{array}{cc}
5x - 8y = -23 & \quad \text{(1)} \\
-4x - 6y = 6 & \quad \text{(2)}
\end{array}
$$

#### Step 1: Row Operations to Get a Leading 1 in the First Row

Divide the first row by 5:

$$
\begin{bmatrix}
1 & -\frac{8}{5} & -\frac{23}{5} \\
-4 & -6 & 6
\end{bmatrix}
$$

#### Step 2: Eliminate the Coefficient Below the Leading 1

Add 4 times the first row to the second row:

$$
\begin{bmatrix}
1 & -\frac{8}{5} & -\frac{23}{5} \\
0 & -\frac{46}{5} & -\frac{46}{5}
\end{bmatrix}
$$

#### Step 3: Scale the Second Row

Multiply the second row by $-\frac{5}{46}$:

$$
\begin{bmatrix}
1 & -\frac{8}{5} & -\frac{23}{5} \\
0 & 1 & 1
\end{bmatrix}
$$

#### Step 4: Eliminate the Coefficient Above the Leading 1

Add $\frac{8}{5}$ times the second row to the first row:

$$
\begin{bmatrix}
1 & 0 & -3 \\
0 & 1 & 1
\end{bmatrix}
$$

#### 2. Solution via Row Reduction

> [!done]
>
> The system is now in row-echelon form. The solution is $x = -3$ and $y = 1$.

### 2. The Naive - Substitution Method

$$
\begin{align*}
5x - 8y &= -23 \\
-4x - 6y &= 6
\end{align*}
$$

#### Step 1: Solve one equation for one variable

Solve the first equation for $x$:

$5x = 8y - 23$

$x = \frac{8y - 23}{5}$

#### Step 2: Substitute the expression into the other equation

Substitute the expression for $x$ into the second equation:

$-4x - 6y = 6$

$-4\left(\frac{8y - 23}{5}\right) - 6y = 6$

#### Step 3: Solve for the variable

Simplify and solve for $y$:

$-\frac{32y - 92}{5} - 6y = 6$

$-32y + 92 - 30y = 30$

$-62y + 92 = 30$

$-62y = -62$

$y = 1$

#### Step 4: Substitute the solution back

Substitute the value of $y$ back into the expression for $x$:

$x = \frac{8y - 23}{5}$

$x = \frac{8(1) - 23}{5}$

$x = -3$

#### 2. Solution via the Naive - Substitution Method

> [!done]
>
> The solution to the system of equations is $x=−3$ and $y=1$.

## 3. (1 point) Solve the following system

> [!info] Solve the following system
>
> $$
> \huge
> {\begin{align*}
> x-2y-z&=&-4 \\
> y-3x+z&=&3 \\
> -2y-z&=&2
> \end{align*}}
> $$

### 3. Strategy: Row Reduction

### 3. The Naive - Substitution Method

## 4. (1 point) For what value(s) of _h_ is the linear system consistent?

> [!info] For what value(s) of _h_ is the linear system consistent?
>
> $$
> \huge
> {\begin{align*}
> -&6x_1&{}&-{}&8x_2&=&h \\
> &9x_1&{}&+{}&12x_2&=&-1
> \end{align*}}
> $$
>
> _h_ \[is equal to/ is not equal to\] \_\_\_\_\_\_\_\_\_\_\_

### 4. Strategy: Row Reduction

### 4. The Naive - Substitution Method
