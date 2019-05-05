### Optimizing database queries

1. #### Indexing

	A database index is a data structure that improves the speed of operations in a table.

	Every time your web application runs a database query, the database will look through all the rows in your table to 	    find those that match your request. As your database tables grow, an increasing number of rows need to be inspected 	each time which can slow the overall performance of the database and respectively your application.
	
	1. To find the rows matching a WHERE clause quickly.
	
	2. To eliminate rows from consideration. If there is a choice between multiple indexes, MySQL normally uses the index that finds the smallest number of rows

	3. If the table has a multiple-column index, any leftmost prefix of the index can be used by the optimizer to look up rows
	
	MySQL indexes operate by taking data from a column in your table and storing it alphabetically in a separate location 	      called an index.
	
	Example:
	
	`SELECT * FROM employees WHERE number = 7;`
	
	MySQL will check all records and will return only the one that has its number value set to 7.
	
	Let me add an index:
	
	`ALTER TABLE employees ADD INDEX (number);`
	
	Once this index is set, next time you I to get the information for employee number 7, the service will go directly             to it using the index and will return the information much faster.
