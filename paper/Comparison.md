# Comparison with other database systems
The following chapters will compare graph databases, especially neo4j with other database systems such as relational databases and NoSQL (not only SQL) databases. In addition to plain comparisons there will also be some examples how graph databases can be used with other systems to maximmize the advantages of each system.
## Comparison with relational databases
This chapter will give a basic overview of the similiarities and differences between graph databases and relational databases. More specifically this chapter will focus on neo4j and SQL. 
In neo4j relationships are first-class citizens. In SQL these relationships can only be created by using foreign keys and therefore neo4j eliminates foreign keys. Each node contains a list of relationship-records. These relationship-records are organized by type and direction and can hold additional attributes. When you would normally run a JOIN-operation these records are used. This is the biggest advantage graph databases have over relational databases: The costs of expensive search and match operations are eliminated.
This leads to much higher performance levels than those of relational databases.
In additiont the data models of graph databases are simpler and more expressive.
Like SQL neo4j also supports the transactional concepts (ACID). That means that data is never lost after it has been commited to the database.
The query language is pretty similiar, although cypher, the query language of neo4j is more expressive.
Following is a short comparison of the same transaction in SQL and Cypher. This example also demonstrates the strength of Cypher by eliminating two JOIN-operations.
### Cypher Statement
```Cypher
MATCH (p:Person)<-[:EMPLOYEE]-(d:Department)
WHERE d.name = "IT Department"
RETURN p.name
```
### SQL Statement
```SQL
SELECT name FROM Person
LEFT JOIN Person_Department
  ON Person.Id = Person_Department.PersonId
LEFT JOIN Department
  ON Department.Id = Person_Department.DepartmentId
WHERE Department.name = "IT Department"
```
## Comparison with NoSQL databases

## Integration with MongoDB

## Integration with Cassandra
