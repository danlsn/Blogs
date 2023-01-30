# LAG() & LEAD() | Advanced SQL Functions

**This is the second post in an N-Post series on Advanced SQL with a focus on Window
Functions. You can find the first post here
[Intro to Window Functions in SQL.](https://www.thedataschool.com.au/daniel-lawson/introduction-to-window-functions-advanced-sql/)
Stick around to level up your SQL skills.**


<!-- Preamble -->

## Preamble

`LAG()` and `LEAD()` are two of the most useful window functions in SQL. They allow you to access values from rows 
"above" or "below" the current row. This is quite useful for queries where you want to compare values or make 
calculations based on past or future values.

For example, using `LAG()` you can calculate the change in a monthly sales figure from the previous month. However, 
you're not limited to just the previous row. You can use `LAG()` to access any row in the window partition. You 
could choose to access the row from 6 months ago, or the row from 2 years ago. The choice is yours.

## Data Used in this Post

For this post, we'll be using a dataset containing my personal Spotify listening history stored in a PostgreSQL 
database. 

## LAG()

`LAG()` is a window function that looks backwards and returns the value of a row that is offset by a specified 
number of rows. The syntax is as follows:

```sql
LAG(column, offset, default)
```

<!--  -->

______________________________________________________________________
