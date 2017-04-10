# Cypher

Cypher is Neo4j’s open graph query language. It was newly created to match the data-structures of Neo4j and to fulfill the special needs of Graph-Databases.
In addition it's based on SQL to allow an easy entry point for developers, which already had to work with SQL. (Neo Technology, Inc., 2017b, "About Cypher", para. 1)
Cypher’s syntax provides a familiar way to match patterns of nodes and relationships in the graph.
Cypher is also a relatively simple but still very powerful language.
Very complicated database queries can easily be expressed through Cypher.
This allows users to focus on their domain instead of getting lost in database access because it allows the user to state what he wants to select, insert, update or delete from his graph data without requiring him to describe exactly how to do it.

## Example

Cypher contains a variety of clauses. 
Among the most common are: MATCH and WHERE. (Neo Technology, Inc., 2017c, "A few words about Cypher", para. 3)
These functions are slightly different than in SQL.
MATCH is used for describing the structure of the pattern searched for, primarily based on relationships.
WHERE is used to add additional constraints to patterns.
For example, the below query will return all movies starting with "T", and return its cast as a collection:
```
MATCH (actor:Person)-[:ACTED_IN]->(movie:Movie)  
WHERE movie.title STARTS WITH "T"  
RETURN movie.title AS title, collect(actor.name) AS cast  
ORDER BY title ASC LIMIT 10;
```

## ASCII-Art and Nodes

Cypher uses ASCII-Art to represent patterns. It surrounds nodes with parentheses which look like circles, e.g. **(node)**. (Neo Technology, Inc., 2017b, "Nodes", para. 1)

![node ascii art](/paper/images/cypher_pattern_simple.png)

To reference a node at a later time, it can be stored in a variable like (p) for person or (t) for thing.
In real-world queries, there would probably be longer, more expressive variable names like (person) or (thing).
If the node is not relevant to the question, the parenthesis can also be empty ().

## Relationships

To fully utilize the power of graph databases complex patterns between the nodes can be expressed.
Relationships are basically an arrow **-->** between two nodes. (Neo Technology, Inc., 2017b, "Relationships", para. 1)
Additional information can be placed in square brackets inside of the arrow.

This can be

- relationship-types like **-[:KNOWS|:LIKE]->**
- a variable name **-[rel:KNOWS]->** before the colon
- additional properties **-[{since:2010}]->**
- structural information for paths of variable length **-[:KNOWS\*..4]->**
(Neo Technology, Inc., 2017b, "Relationships", para. 3)

## Create a Record

```
CREATE (you:Person {name:"You"})
RETURN you
```
**CREATE** creates nodes with labels and properties.

![graph you](/paper/images/you.png)

## Create Relations

```
MATCH (you:Person {name:"You"})
FOREACH (name in ["Tobias","Kai","Manuel"] |
  CREATE (you)-[:FRIEND]->(:Person {name:name}))
```
**FOREACH** allows the execution of update operations for each element of a list.

## Show Relations

```
MATCH (you {name:"You"})-[:FRIEND]->(yourFriends)
RETURN you, yourFriends
```

![graph friends](/paper/images/friends.png)


***
References:

- Neo Technology, Inc. (2017a). _Cypher Query Language Developer Guides & Tutorials._ Retrieved April 9, 2017, from https://neo4j.com/developer/cypher/
- Neo Technology, Inc. (2017b). _Neo4j's Graph Query Language: An Introduction to Cypher._ Retrieved April 9, 2017, from https://neo4j.com/developer/cypher-query-language/
- Neo Technology, Inc. (2017c). _For Relational Database Developers: A SQL to Cypher Guide._ Retrieved April 9, 2017, from https://neo4j.com/developer/guide-sql-to-cypher/
- Mahler, D. (2014). _Graphendatenbank: Flexible Datenabfragen mit Neo4j._ Retrieved April 9, 2017, from https://www.heise.de/developer/artikel/Graphendatenbank-Flexible-Datenabfragen-mit-Neo4j-2176439.html
- Panzarino, O. (2014). _Learning Cypher._ CA: Packt Publishing Ltd
