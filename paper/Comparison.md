# Comparison with other database systems
The following chapters will compare graph databases, especially Neo4j with other database systems such as relational databases and NoSQL (not only SQL) databases. In addition to plain comparisons there will also be some examples how graph databases can be used with other systems to maximmize the advantages of each system.
## Comparison with relational databases
This chapter will give a basic overview of the similiarities and differences between graph databases and relational databases. More specifically this chapter will focus on Neo4j and SQL. 
In Neo4j relationships are first-class citizens. In SQL these relationships can only be created by using foreign keys and therefore Neo4j eliminates foreign keys. Each node contains a list of relationship-records. These relationship-records are organized by type and direction and can hold additional attributes. When you would normally run a JOIN-operation these records are used. This is the biggest advantage graph databases have over relational databases: The costs of expensive search and match operations are eliminated.
This leads to much higher performance levels than those of relational databases.
In addition the data models of graph databases are simpler and more expressive.
### SQL data model
![sql data model](/paper/images/organization_relational.png)
### Neo4j data model
![Neo4j data model](/paper/images/organization_graph.png)
Graph DB vs RDBMS. https://neo4j.com/developer/graph-db-vs-rdbms/

Like SQL Neo4j also supports the transactional concepts (ACID). That means that data is never lost after it has been commited to the database.
The query language is pretty similiar, but cypher, the query language of Neo4j, is more expressive.
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

Webber, J. & Robinson, I. (2015) *Graph Databases*. O'Reilly
## Integration with other database systems
This chapter will describe how to use Neo4j together with other database systems in a very basic way. It will not go in-depth and there will be no code examples to keep it as simple as possible.
To get the advantages of each database system, data needs to be stored in each database with its own data models. This is called polyglot programming: using multiple different languages, here multiple different database systems. There are existing tools for different database systems which can be used as some kind of connector to another system. The connectors let the other system subscribe to update events, so the data can be inserted in one database system and then added in the other system. The developers of MongoDB for example have created a tool called "mongo-connector" where other applications can listen for update events. This enables a one-way synchronization with Neo4j. Of course all the data model transformations have to be made manually, but once set up the full potential of both databases can be used.

