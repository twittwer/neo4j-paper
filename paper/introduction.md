# Introduction to Graph Databases

Nowadays a huge number of different databases systems exists. You always must select the best suiting one for your specific use case. Data is often ordered in relations between objects, like different cities and their connecting streets. 
If there is the possibility to structure your data in the database in the same way as the data is structured in real life, you may get a speed and usability advantage out of that. The best solution to picture these structures is to use the graph. That is why graph databases have been developed, which now will be presented to you.

## Graph Databases

Graph databases uses graph structure to order data in the database. There is more than one solution for using graphs. The main aspects of the first are nodes and edges, which are essential for the database structure (Robinson, Webber, & Eifrem, 2013, pp. 1-4).
The connection between the nodes are the relations of the data. In the example picture below (Rouse, 2016, para. 1), you can see how graph databases work with the nodes and their relations. For example you can see the married couple Julie and Bob.

[![ExampleGraph](/paper/images/IntroExampleGraph.JPG)](
http://whatis.techtarget.com/definition/graph-database)

You can also build property graphs, which you can use for routing. For example, you can find the shortest way from one city to another. The special thing about property graphs is, that attributes can be added to the nodes and edges. So you can store further information in your graph (Rodriguez, & Neubauer, 2010, p. 3).

The second one is used for the semantic web and concentrates on triples. Semantic web stands for machine processable web. In the semantic web the W3C consortium defined a framework how to work with the triples (W3C, 2014, "Overview", para. 1). It is called Resource Description Framework and its structure is like following:

- First part: subject, where the relation starts. 
- The second: predicate, the relation 
- The third: object, where the predicate points to. 

Despite you can see the same node and edge structure, it is different to the property graphs. In Resource Description Framework, which is the most common used framework,  you can only build connections between the nodes, but you can nether set properties to the nodes nor to the edges.

## Neo4j

Neo4j - developed by Neo Technology - is one of the first and up to now the most popular graph database implementations. Neo4j has a more than fife times higher popularity rate as the second graph database - OrientDB (Solid IT Gmbh, 2017, para. 1).<br>
Its first Version was released in 2010 after three years of development. It is called as transactional, disk based database, which follows the ACID principle (Neo Technology, Inc., 2017b, "Neo4j Internals", para. 4). The implementation is in Java and can be used in two different license models. The Community and the Enterprise Edition.<br>
The Community Edition is for free, but only running on a single node. You can use all the features of Neo4j without high availability through clustering and hot backup. 
These additional modules are coming with the Enterprise Edition only. There are some further categorizations for the Enterprise version like the test licenses Evaluation, the Educational and the Neo4j Loves Open Source licenses (Neo Technology, Inc., 2017a, "About Neo4j Licenses", para. 1).<br>
Neo4j uses Cypher as query language. With indexing and the labels of the graph it helps to accelerate the queries, which is one of the main advantage of using graph databases and especially Neo4j.

Now you get a deeper insight into Neo4j and its data structure.

***
References:

- Neo Technology, Inc. (2017a). _Neo4j Licensing._ Retrieved April 9, 2017, from https://neo4j.com/licensing/
- Neo Technology, Inc. (2017b). _Neo4j: The World’s Leading Graph Database._ Retrieved April 9, 2017, from https://neo4j.com/product/
- Robinson, I., Webber, J., & Eifrem, E. (2013). _Graph Databases._ Sebastopol, CA: O'Reilly Media
- Rodriguez, M. A., & Neubauer, P. (2010). _Constructions from Dots and Lines._ Retrieved from the Cornell University website: https://arxiv.org/abs/1006.2361
- Rouse, M. (2016). _DEFINITION: graph database._ Retrieved April 5, 2017, from http://whatis.techtarget.com/definition/graph-database
- Solid IT Gmbh (2017). _DB-Engines Ranking von Graph DBMS._ Retrieved April 8, 2017, from https://db-engines.com/de/ranking/graph+dbms
- W3C (2014). _Resource Description Framework (RDF)._ Retrieved April 9, 2017, from https://www.w3.org/RDF/
