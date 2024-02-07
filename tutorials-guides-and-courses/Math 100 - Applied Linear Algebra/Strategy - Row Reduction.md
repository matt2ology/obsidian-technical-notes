---
aliases:
note-type: permanent
date-created: 2024-02-01
long-form-date-created: Thursday, February 01, 2024
week-created: Week 05.4
time-created: 10:45 AM
---

# Strategy - Row Reduction

Related :

> [!info] Strategy: Row Reduction
>
> To transform a matrix to REF or REF, use the following algorithm.
>
> 1. Find the leftmost nonzero column—this is called the pivot column.
> 2. Choose a nonzero entry in the pivot column—this will be called the pivot. If necessary, use interchange operations to make sure the pivot is in the top row.
> 3. Use replacement operations to create zeros below the pivot.
> 4. Cover up (or ignore) the row containing the pivot, and repeat steps 1–3 on the smaller matrix below. Continue repeating until there are no more nonzero rows to modify.
>
> At this point, the matrix is in REF. To transform to RREF, continue with the process below.
>
> 5.  Beginning with the rightmost pivot, working up and to the left, use replacement operations to create zeros above each pivot. If a pivot is not 1, use a scaling operation to make it 1.
>
> At this point, the matrix is in RREF.

## 1. Row reduce the following matrix to RREF, and determine if the corresponding linear system corresponding is consistent or not

$$
\Huge
\left[\begin{matrix}1&3&5&7\\ 3&5&7&9\\ 5&7&9&1\end{matrix}\right]
$$

$$
\left[\begin{matrix}1&3&5&7\\ 3&5&7&9\\ 5&7&9&1\end{matrix}\right]
$$
