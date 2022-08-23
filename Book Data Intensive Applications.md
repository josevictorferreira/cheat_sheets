# Book: Data Intensive Applications

### NoSQL vs SQL

 - Don't use NoSQL databases when there are Many To Many relations in your data.
 - Use NoSQL when the data don't has many relations, and when the nested data related is always needed together the main document. Ex: User collection with an Address data nested inside.
 - SQL databases are also easier to made changes in the structure or a format of a existing data.
 - NoSQL doesnt enforce any schema on the data. It uses the Schema-on-read.
 
### Graph-Like Data Models

- If many-to-many relationships are very common in your data, SQL handles simple cases of many-to-many relationships, but as the connections within your data become more complex, it becomes natural to start modeling your data as a graph
- We can use a SQL relational database to store a graph, but it's difficult to query since the number of joins needed may be not fixed in advance.