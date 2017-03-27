# Comparison with other database systems
The following chapters will compare graph databases, especially neo4j with other database systems such as relational databases and NoSQL (not only SQL) databases. In addition to plain comparisons there will also be some examples how graph databases can be used with other systems to maximmize the advantages of each system.
## Comparison with relational databases
This chapter will give a basic overview of the similiarities and differences between graph databases and relational databases. More specifically this chapter will focus on neo4j and SQL. 
In neo4j relationships are first-class citizens. In SQL these relationships can only be created by using foreign keys and therefore neo4j eliminates foreign keys. Each node contains a list of relationship-records. These relationship-records are organized by type and direction and can hold additional attributes. When you would normally run a JOIN-operation these records are used. This is the biggest advantage graph databases have over relational databases: The costs of expensive search and match operations are eliminated.
This leads to much higher performance levels than those of relational databases.
In addition the data models of graph databases are simpler and more expressive.
### SQL data model
![sql data model](/paper/images/organization_relational.png)
### neo4j data model
![neo4j data model](/paper/images/organization_graph.png)

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
Since relationships are very important in graph databases, it's quite difficult to compare them with NoSQL databases, since they lack relations. Following statement explains this scenario in a good way:
>Most NoSQL databases store sets of disconnected aggregates. This makes it difficult to use them for connected data and graphs.
>One well-known strategy for adding relationships to such stores is to embed an aggregate’s identifier inside the field belonging to another aggregate — effectively introducing foreign keys.
>But this requires joining aggregates at the application level, which quickly becomes prohibitively expensive.
(Graph Databases, O’Reilly: Jim Webber, Ian Robinson)
## Integration with MongoDB
This chapter will describe how to use both neo4j and MongoDB together in a very basic way. It will not go in-depth and there will be no code examples to keep it as simple as possible.
To get the advantages of both databases (the quick look-up of data from MongoDB and the quick relationship search of neo4j), data needs to be stored in each database with its own data models. The developers of MongoDB have created a tool called "mongo-connector" where other applications can listen for update events. This enables a one-way synchronization with neo4j. Of course all the data model transformations have to be made manually, but once set up the full potential of both databases can be used.
## Integration with Cassandra
<!---
TODO:
Maybe rename to "Integration with other databases" and merge those 2 since they are similar.
-->
