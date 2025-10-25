# Modern SQL:

# Aggregate Functions:

Functions that return a single value from a bag of 
tuples:
→ AVG(col)→ Return the average col value.
→ MIN(col)→ Return minimum col value.
→ MAX(col)→ Return maximum col value.
→ SUM(col)→ Return sum of values in col.
→ COUNT(col)→ Return # of values for col.


<img width="795" height="450" alt="image" src="https://github.com/user-attachments/assets/2ace5187-acc4-424e-9523-5e96bbd54404" />

Here, you're trying to select AVG(s.gpa) (an aggregate function)

and e.cid (a regular, non-aggregated column)

❌ This will generate an SQL error because you're mixing an aggregate function with a regular column without a GROUP BY clause.

SQL won't know:

"I'm getting one value for the average GPA from all rows, but which cid should I choose? In so many rows!"


# STRING OPERATIONS:

<img width="889" height="441" alt="image" src="https://github.com/user-attachments/assets/4f54590b-0cb9-423b-94f3-7bb411a05ea5" />



# Window functions:

# - Row_number -

When there is no PARTITION BY:

It means that SQL treats the entire table as one single group (one window).
All the rows belong to the same window,
so ROW_NUMBER() numbers the entire table from the first row to the last row
based on the column specified in the ORDER BY clause or create the row call like after as ex) row_num.

<img width="934" height="485" alt="image" src="https://github.com/user-attachments/assets/b3bccc87-a79e-4c1d-afb7-be5d143fab8e" />

# - Row_number -

When there is a PARTITION BY:

It means that SQL divides the table into multiple groups (partitions) based on the column(s) specified after PARTITION BY.
Each partition acts like a separate mini-table, and the window function (like ROW_NUMBER()) works independently inside each partition.
So the numbering starts again from 1 within every partition.

<img width="975" height="545" alt="image" src="https://github.com/user-attachments/assets/74591138-184f-4e29-83b2-53b40dadcdcb" />

important notes: The OVER keyword specifies how to
group together tuples when
computing the window function.
Use PARTITION BY to specify group.



