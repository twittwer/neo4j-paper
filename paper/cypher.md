# Cypher

Cypher is Neo4j’s open graph query language. It was newly created to match the data-structures of Neo4j and to fulfill the special needs of Graph-Databases.
In Addition it's based on SQL to allow an easy entry point for developer, which already had to work with SQL.
Cypher’s syntax provides a familiar way to match patterns of nodes and relationships in the graph.
Cypher is also a relatively simple but still very powerful language.
Very complicated database queries can easily be expressed through Cypher.
This allows users to focus on their domain instead of getting lost in database access because it allows the user to state what he wants to select, insert, update or delete from his graph data without requiring him to describe exactly how to do it.

## Example

Cypher contains a variety of clauses. 
Among the most common are: MATCH and WHERE.
These functions are slightly different than in SQL.
MATCH is used for describing the structure of the pattern searched for, primarily based on relationships.
WHERE is used to add additional constraints to patterns.
For example, the below query will return all movies starting with "T", and return it's cast as collection:
```
MATCH (actor:Person)-[:ACTED_IN]->(movie:Movie)  
WHERE movie.title STARTS WITH "T"  
RETURN movie.title AS title, collect(actor.name) AS cast  
ORDER BY title ASC LIMIT 10;
```

## ASCII-Art and Nodes

Cypher uses ASCII-Art to represent patterns. We surround nodes with parentheses which look like circles, e.g. **(node)**.

![node ascii art](/paper/images/cypher_pattern_simple.png)

If you want to refer to the node later, you can give it an variable like (p) for person or (t) for thing.
In real-world queries, you would probably use longer, more expressive variable names like (person) or (thing).
If the node is not relevant to your question, you can also use empty parentheses ().

## Relationships

To fully utilize the power of our graph database we want to express more complex patterns between our nodes.
Relationships are basically an arrow **-->** between two nodes.
Additional information can be placed in square brackets inside of the arrow.

This can be

- relationship-types like **-[:KNOWS|:LIKE]->**
- a variable name **-[rel:KNOWS]->** before the colon
- additional properties **-[{since:2010}]->**
- structural information for paths of variable length **-[:KNOWS\*..4]->**

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
**FOREACH** allows you to execute update operations for each element of a list.

## Show Relations

```
MATCH (you {name:"You"})-[:FRIEND]->(yourFriends)
RETURN you, yourFriends
```

![graph friends](/paper/images/friends.png)

