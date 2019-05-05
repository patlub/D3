### Optimizing database queries

1. #### Indexing

	Indexes are used to find rows with specific column values quickly. Without an index, SQL must begin with the first row and then read through the entire table to find the relevant rows. The larger the table, the more this costs. If the table has an index for the columns in question, MySQL can quickly determine the position to seek to in the middle of the data file without having to look at all the data. This is much faster than reading every row sequentially.
