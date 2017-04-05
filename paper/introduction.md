# Introduction to Graph Databases

Nowadays a huge number of different databases systems exists. You always must select the best suiting one for your specific use case. Data is often ordered in relations between objects and connections.
If there is the possibility to structure your data in the database in the same way as the data is structured in real life, you may get a speed and usability advantage out of that. The best solution to picture these structures is to use the graph. That is why graph databases have been developed, which now will be presented to you.

## Graph Databases

[//]: # (include some of them?
         - Abfragesprachen
         - Algorithmen
         )

Graph databases uses graph structure to order data in the database. There is more than one solution for using graphs. The main aspects of the first are nodes and edges, which are essential for the database structure. [[Graph Databases: New Opportunities p.1ff]](https://books.google.de/books?id=RTvcCQAAQBAJ&printsec=frontcover&dq=graph+database&hl=de&sa=X&redir_esc=y#v=onepage&q=graph%20database&f=false)

[//]: # (Here is a picture of a graph)
         
The connection between the nodes are the relations of the data. You can especially build property graphs, which you can use for routing. For example, you can find the shortest way from one city to another.
The second one is used for the sematic web and concentrates on triples. Semantic web stands for machine processable web. In the semantic web the W3C consortium definde a framework how to work with the triples. The first part is the subject, where the relation starts. The second one is the predicate and the third is the object, where the predicate points to. [2 times sourcen: 1x w3c] 
Despite you can see the same node and edge structur, it is different to the property graps. In Resource Description Framework, which is the most common used framework [source],  you can only build connections between the nodes, but you can nether set propertys to the nodes nor to the edges.

## Neo4j

[//]: # (further edits?)

Neo4j - developed by Neo Technology - is one of the first and up to now under the most popular graph database implementations.[benchmark source] Its first Version was released in 2010 after three years of development. It is called as transactional, disk based database, which follows the ACID principle. The implementation is in Java and can be used in two different licensmodels. The Community and the Enterprise Edition.
The Community Edition is for free, but only running on a single node. You can use all the features of Neo4j without high availability through clustering and hot backup. 
These aditional modules are comming with the Enterprise Edition only. There are some further categorications for the Enterprise version like the test licences Evaluation, the Educational and the Neo4j Loves Open Source licenses.
Neo4j uses Cypher as query language. With indexing and the lables of the graph it helps to accelerate the queries, which is one of the main advantage of using graphdatabases and especially Neo4j.

[//]: # (Conclusion
    How does CAP theorem apply to neo4j? MK
         )
         
[//]: # (Neo4j is not partition tolerant. Automatic, domain agnostic graph sharding is still a problem that we have to solve to scale out. [See also the thesis of Alex Averbuch: http://alexaverbuch.blogspot.com/2010/04/me-my-names-alex-im-currently.html]        
-Who uses neo4j)









