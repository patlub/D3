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
	
1. #### Partitioning

	Partitioning enables the distribution of portions of individual tables across a file system according to rules which you can set largely as needed. In effect, different portions of a table are stored as separate tables in different locations. The user-selected rule by which the division of data is accomplished is known as a partitioning function
	
 Examples:
 
	 `CREATE TABLE members (
	    firstname VARCHAR(25) NOT NULL,
	    lastname VARCHAR(25) NOT NULL,
	    username VARCHAR(16) NOT NULL,
	    email VARCHAR(35),
	    joined DATE NOT NULL
	)
	PARTITION BY KEY(joined)
	PARTITIONS 6;`

	`CREATE TABLE members (
	    firstname VARCHAR(25) NOT NULL,
	    lastname VARCHAR(25) NOT NULL,
	    username VARCHAR(16) NOT NULL,
	    email VARCHAR(35),
	    joined DATE NOT NULL
	)
	PARTITION BY RANGE( YEAR(joined) ) (
	    PARTITION p0 VALUES LESS THAN (1960),
	    PARTITION p1 VALUES LESS THAN (1970),
	    PARTITION p2 VALUES LESS THAN (1980),
	    PARTITION p3 VALUES LESS THAN (1990),
	    PARTITION p4 VALUES LESS THAN MAXVALUE
	);`

	`CREATE TABLE trb3 (id INT, name VARCHAR(50), purchased DATE)
	    PARTITION BY RANGE( YEAR(purchased) ) (
		PARTITION p0 VALUES LESS THAN (1990),
		PARTITION p1 VALUES LESS THAN (1995),
		PARTITION p2 VALUES LESS THAN (2000),
		PARTITION p3 VALUES LESS THAN (2005)
	    );`
    
	`CREATE TABLE t3 (
	    fname VARCHAR(50) NOT NULL,
	    lname VARCHAR(50) NOT NULL,
	    region_code TINYINT UNSIGNED NOT NULL,
	    dob DATE NOT NULL
	)
	PARTITION BY LIST(region_code) (
	    PARTITION r0 VALUES IN (1, 3),
	    PARTITION r1 VALUES IN (2, 5, 8),
	    PARTITION r2 VALUES IN (4, 9),
	    PARTITION r3 VALUES IN (6, 7, 10)
	);`

	`SELECT * FROM employees PARTITION (p1);`

	`SELECT * FROM employees PARTITION (po, p2) WHERE lname LIKE 'S%'`

3. #### Clustering

	Database Clustering is the process of combining more than one servers or instances connecting a single database. Sometimes one server may not be adequate to manage the amount of data or the number of requests, that is when a Data Cluster is needed. Database clustering, SQL server clustering, and SQL clustering are closely associated with SQL is the language used to manage the database information.
	
	The main advantages of database clustering are; Data redundancy, Load balancing, High availability, and lastly, Monitoring and automation.
	
4. #### Striping

	Data striping is the technique of segmenting logically sequential data, such as a file, so that consecutive segments are stored on different physical storage devices. In databases, this is mostly essential during data backups
Striping is useful when a processing device requests data more quickly than a single storage device can provide it. By spreading segments across multiple devices which can be accessed concurrently, total data throughput is increased. It is also a useful method for balancing I/O load across an array of disks.
