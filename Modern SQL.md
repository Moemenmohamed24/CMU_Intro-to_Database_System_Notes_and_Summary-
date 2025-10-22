# Modern SQL:

<img width="821" height="461" alt="image" src="https://github.com/user-attachments/assets/4c2c906b-9a35-481e-acf0-70ea8e656c97" />

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
