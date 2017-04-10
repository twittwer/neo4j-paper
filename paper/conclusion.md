# Conclusion

In the end you can say that Graph databases, and therefore also Neo4j, don't need joins to achieve relationships, since they are already first-class citizens. This has a huge impact on performance, since join-operations are very expensive.
As Neo4j holds its data as JSON it has a similiar structure to document based databases and could be used together. That way you can get the advantages of both systems. The only disadvantage is the need to store the whole data twice, which requires more storage. 

In general Neo4j fullfills the CAP-theorem in points of **c**onsistency and **a**vailablity and doesn't provide **p**artition tolerance. Because Neo4j is relationship-oriented, trying to achieve partition tolerance can cause many side effects and complex queries would decrease the performance considerable.

Neo4j has many use cases. For example it is used by companies such as Walmart for real-time recommendations, Ebay for logistics, LinkedIn as a representation for their Social Network and TomTom for geo-routing. An interessting fact at this point was published by the Neo4j staff. They said Neo4j is not used by Facebook, which "they should" change (Neo4j Staff, 2011, para. 5).<br>

Neo4j is mainly used for relational analytics and is hence not efficient unless you have many joins. The following chart will enforce this statement.<br>
![neo4j sql comparison](/paper/images/neo4j_joins.PNG)<br>
(Dhaval Dalal, 2014, slide 19).<br>
As shown in the graph, Neo4j's full potential unleashes when many join-operations are executed as the query execution time stays constantly low, whereas the execution time for inner joins in MySQL rises exponentially. Another performance aspect is, that Neo4j in its second version can automatically index often used Nodes and gets an additional speed advantage at run time.

Overall Neo4j is quite unique, but has high potential in the sector of relational databases.
It is useful to perform complex relational data queries and can be used for many different business cases.
It is still the most popular graph database and some weaknesses can be handled by using Neo4j with another NoSQL database together.

***
> ## Sources
> - Neo4j Staff (2011) _Intro to Graph Databases._ Retrieved April, 9, 2017, from https://neo4j.com/blog/recap-intro-to-graph-databases-webinar-series-1/
> - Dhaval Dalal (2014). _Neo4j MySql MS-SQL comparison._ Retrieved April, 9, 2017, from https://de.slideshare.net/DhavalDalal/neo4j-my-sqlmssqlcomparisonfinal
