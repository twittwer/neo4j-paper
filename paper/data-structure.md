## Data Structures

In opposite to the bulk of NoSQL databases Neo4j as a graph database is focused on the relationships between data.
Therefore the data structure is based on two components: nodes and relationships. Both of them can contain a variety of informations.
Let’s start with the nodes. Each node consists of a JSON object which defines its properties, so the nodes can be compared to documents in MongoDB for example. In the definition of this node properties you can use anything, that’s provided by the JSON standard. In a library for example we could have books with properties about their title, page number or publication date.
With this properties we get the ability to store data and in connection with the later introduced cypher query language we can search for nodes by them. But currently searches would be executed over the whole graph and any node can contain different properties.
(Neo Technology, Inc., 2017a, "Nodes", para. 3) (Gupta, 2015, p. 80) (Hunger, 2013, slide 20-21)

![Single Book Node](/paper/images/data-structure/single-node.png)

To structure the data, every node can be labeled. This labels can be interpreted as  a typing. Looking back at our library example we could create nodes labeled as “book”, “author” or “borrower”. By labeling the node we organize them in sets, like the MongoDB collections or SQL tables.
Beside the better structure we achieve a more efficient searching, because the amount of data to search in can be reduced right at the beginning, by the definition of the node set (label) to search in.
At this point we have nodes with properties organized in sets by their labels, but no relationships.
(Neo Technology, Inc., 2017a, "Labels", para. 2) (Hunger, 2013, slide 26-27)

![Labeled Node Sets](/paper/images/data-structure/labeled-nodes.png)

The relationships in Neo4j are quite similar to the nodes. They are also able to take properties in form of JSON objects and has labels to define their type or in this case better to say their function. In the library example a relationship between book and borrower could be labeled as “borrowed” and contains properties like “borrowDate”, “returnDate” or maybe “rating”. Here we should also have a look at a good structure, so it would be better to extract the rating and put it in another relationship like “read”.
The main and obvious difference are the two connected nodes. So every relationship needs exactly two nodes connected to it. But they do not have to be different, so it’s possible to point a relationship on its own origin. Naturally the node labels are irrelevant here, so relationships can be defined inside and between node sets.
(Neo Technology, Inc., 2017a, "Relationships", para. 1) (Gupta, 2015, p. 81-82) (Hunger, 2013, slide 22-25)

![Related Nodes](/paper/images/data-structure/node-relationships.png)

After looking at the elements of the Neo4j data structure, we will now have a look at how we create this structure in our database instance.
At first it’s necessary to create some nodes. Therefore we use the CREATE command followed by round brackets to define the node itself. The first element of the node definition is an optional variable name at first to save the reference to the created node, if needed. After this a colon and label name is required to define the node set. The label doesn’t need to be defined before using it here. At last we enter the JSON object with our node properties and close the definition brackets.
(Neo Technology, Inc., 2017b, "Create a Record for Yourself", para. 1) (Gupta, 2015, p. 80)

```
CREATE ( variable:LABEL {} )
CREATE ( theLordOfTheRings:Book { title: ‘The Lord Of The Rings’, publication_date: ‘1954-07-29’ } )
CREATE ( jrrTolkien:Author { name: ‘J. R. R. Tolkien’ } )
CREATE ( johnSmith:Borrower { name: ‘John Smith’ } )
```

Secondly we can create the relationships. Thanks to the ascii-art syntax it’s easy to understand the create statements. It starts again with a CREATE and is followed by round brackets. In this case this brackets can contain a node definition again, but also a simple variable name to reference an existing node. After the brackets a hyphen connects the first node to the relationship definition part surrounded by square brackets. This definition is structured like the node definition: optional variable name, label, JSON object. An ascii arrow (“->”) connects the closing square bracket with the second node, this relation will point to. In the style of the first node we have here round brackets with a variable or a  whole node definition.
(Neo Technology, Inc., 2017b, "Create a Record for Yourself", para. 1) (Gupta, 2015, p. 81-82)

```
CREATE (sourceNode)-[ variable:LABEL {} ]->(targetNode)
CREATE (jrrTolkien)-[ :WROTE ]->(theLordOfTheRings)
CREATE (johnSmith)-[ :BORROWED { borrowDate: ‘2017-03-15’, returnDate: ‘2017-04-14’ } ]->(theLordOfTheRings)
```

Below you can have a look at the created graph of the simple example.

![Sample Graph](/paper/images/data-structure/sample-graph.png)


***
> Sources
> - Neo Technology, Inc. (2017a). _Graph Data Modeling Guidelines_. Retrieved March 29, 2017, from https://neo4j.com/developer/guide-data-modeling
> - Neo Technology, Inc. (2017b). _Intro to Cypher_. Retrieved March 29, 2017, from https://neo4j.com/developer/cypher-query-language
> - Gupta, S. (2015). _Neo4j Essentials_. Retrieved from https://books.google.de/books?id=WJ7NBgAAQBAJ
> - Hunger, M. (2013). _Data Modeling with Neo4j_. Retrieved from the SlideShare website: https://de.slideshare.net/neo4j/data-modeling-with-neo4j
