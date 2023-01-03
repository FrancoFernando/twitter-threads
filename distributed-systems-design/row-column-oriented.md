https://twitter.com/Franc0Fernand0/status/1601594867544719360?s=20&t=VtHDVAlWR0fFxQJvbbztog

There are 2 main paradigms used by databases to store data:

• row-oriented
• column-oriented

Here their differences and trade-offs: {1/10} ↓

Row and column oriented paradigms differ for how data is stored into the disk.

Suppose to have this simple table of data:

- column names: ID, Name, Age
- 1st row:               1,  Mark  , 21
- 2nd row:             2,  Julia   , 23

{2/10}

To visualize the difference between the 2 approaches,  think in terms of csv files.

If the disk was a csv file, the above table would be written as:

• ID,Name,Age,1,Mark,21,2,Julia,23

in row-oriented way or

• ID,1,2,Name,Mark,Julia,Age,21,23

in column-oriented way

{3/10}

The row-oriented approach stores the data in a row next to each other.

Since file systems read from the disk in blocks, this makes easier to get all row's data in a single operation.

This is beneficial for databases supporting Online Transaction Processing (OLTP).

{4/10}

OLTP systems usually performs small online transactions with frequent CRUD operations.

Since these only read/write data from/to a group of nearby rows, the row-oriented format is ideal. 

{5/10}

The column-oriented approach stores the data in a column next to each other.

This approach penalizes traditional OLTP queries looking to read/write values in a certain row.

Since the data for the row is not stored together, these queries will require more disk reads.

{6/10}

On the other hand, this approach is beneficial to execute aggregate measures on a column.

Finding the average value for a column will require fewer disks reads. 

This is beneficial for databases supporting Online Transaction Analytics (OLAP).

{7/10}

OLAP systems need to have these characteristics:

- ingest a huge amount of data quickly 
- perform large computation on the data efficiently

Here is where the column-oriented approach shines.

Computations around time-series trends or statistics are more efficient.

{8/10}

But is not only about how the data is stored to the disk. 

Also serialization formats used to tranfer the data can be row or column-oriented.

Row-based formats are the most popular.

CSV, JSON, XML or Apache Avro are all good examples of row-oriented serialization.

{9/10}

Column-oriented serialization formats are less popular.

Examples are Apache Arrow, ORC or Parquet.

These formats have 2 main benefits:

- fewer disk reads for computation on a specific column

- better data compression, since similar values are next to each other

{10/10}



