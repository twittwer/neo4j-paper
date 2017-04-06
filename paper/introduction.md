# Introduction to Graph Databases

Nowadays a huge number of different databases systems exists. You always must select the best suiting one for your specific use case. Data is often ordered in relations between objects and their connections.
If there is the possibility to structure your data in the database in the same way as the data is structured in real life, you may get a speed and usability advantage out of that. The best solution to picture these structures is to use the graph. That is why graph databases have been developed, which now will be presented to you.

## Graph Databases

[//]: # (include some of them?
         - Abfragesprachen
         - Algorithmen
         )

Graph databases uses graph structure to order data in the database. There is more than one solution for using graphs. The main aspects of the first are nodes and edges, which are essential for the database structure. [[Graph Databases: New Opportunities p.1ff]](https://books.google.de/books?id=RTvcCQAAQBAJ&printsec=frontcover&dq=graph+database&hl=de&sa=X&redir_esc=y#v=onepage&q=graph%20database&f=false)
The connection between the nodes are the relations of the data. In the example picture below [rou.M], you can see how graph databases work with the nodes and their relations. For example you can see the married couple Julie and Bob.

[![ExampleGraph](http://itknowledgeexchange.techtarget.com/overheard/files/2014/01/Graph-database-sketch.jpg)](
http://whatis.techtarget.com/definition/graph-database)

You can also build property graphs, which you can use for routing. For example, you can find the shortest way from one city to another. The special thing about property graphs is, that attributes can be added to the nodes and edges. So you can store further information in your graph [rod.M.A p.3].
The second one is used for the semantic web and concentrates on triples. Semantic web stands for machine processable web. In the semantic web the W3C consortium defined a framework how to work with the triples. It is called and its structure is like following:

- First part: subject, where the relation starts. 
- The second: predicate, the relation 
- The third: object, where the predicate points to. 

[2 times sourcen: 1x w3c] 
Despite you can see the same node and edge structure, it is different to the property graphs. In Resource Description Framework, which is the most common used framework [source],  you can only build connections between the nodes, but you can nether set properties to the nodes nor to the edges.

## Neo4j

[//]: # (further edits?)

Neo4j - developed by Neo Technology - is one of the first and up to now under the most popular graph database implementations.[benchmark source] Its first Version was released in 2010 after three years of development. It is called as transactional, disk based database, which follows the ACID principle. The implementation is in Java and can be used in two different license models. The Community and the Enterprise Edition.
The Community Edition is for free, but only running on a single node. You can use all the features of Neo4j without high availability through clustering and hot backup. 
These additional modules are coming with the Enterprise Edition only. There are some further categorizations for the Enterprise version like the test licenses Evaluation, the Educational and the Neo4j Loves Open Source licenses.
Neo4j uses Cypher as query language. With indexing and the labels of the graph it helps to accelerate the queries, which is one of the main advantage of using graph databases and especially Neo4j.

[rod.M.A] (Rodriguez, Marko A. ; Neubauer, Peter: Constructions from dots and lines. In: Bulletin of the American Society for Information Science and Technology 36 (2010), September)
[rou.M] (From Margaret Rouse: Title: graph database, DEFINITION
http://whatis.techtarget.com/definition/graph-database)

[//]: # (Conclusion
    How does CAP theorem apply to neo4j? MK
         )
         
[//]: # (Neo4j is not partition tolerant. Automatic, domain agnostic graph sharding         is still a problem that we have to solve to scale out. [See also the thesis         of Alex Averbuch:http://alexaverbuch.blogspot.com/2010/04/me-my-names-alex-i         m-currently.html])

[//]: # (   - Quellen in APA6 wie auf Moodle beschrieben
            - Who uses neo4j
                - Use Cases
                - Firmen
            )
            
[//]: # (Importend
            - Agenda
            - Introduction
            - Compare to RDBMS
            - Usecase & Companies
            - Demo
            - Conclusion
            )
            


