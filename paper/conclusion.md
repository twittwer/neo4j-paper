# Conclusion

<!--- 
- no joins needed to achive relationships **
- similar structure to other document based dbs => parallel/synced/hybrid usage possible (mongodb) **
- CAP => CA ( relation oriented -> many side effects, complex queries )**
- used by Wallmart (real-time recommandation), Ebay (logistics), LinkedIn (Social Network), TomTom (Geo Routing), !Facebook **
- manly relational analytics -> not performant until you have many joins (https://de.slideshare.net/DhavalDalal/neo4j-my-sqlmssqlcomparisonfinal p.19) **
- auto index popular nodes by time (http://addisonlee.azurewebsites.net/neo4j-vs-mysql-vs-mongodb/)

=> unique and awesome 
-->

In the end you can say that Graph databases, and therefore also Neo4j, don't need joins to achieve relationships, since they are already first-class citizens. This has a huge impact on performance, since join-operations are very expensive.
As Neo4j holds its data as Json it has a similiar structure to document based databases and could therefore be used together. Out of that you can get the advantages of both systems. The only disadvantage is, that you need to hold every data twice and so you need more storage. 

Back to Neo4j. In the CAP-theorem it stands between C and A and is therefore not partition tolerant. Since Neo4j is relationship-oriented trying to achieve partition tolerance can cause many side effects and need complex queries. When you try to get some partition tolerance you lose the other advantages and so there is no use of the hard work.

Neo4j has many use cases. For example it is used by companies such as Walmart for real-time recommendations, Ebac for logistics, LinkedIn as a Social Network and TomTom for GeoRouting. It is however not used by Facebook, which "they should" as told by the Neo4j staff (Neo4j Staff, 2011, para. 5).<br>

Neo4j is mainly used for relational analytics and is hence not efficient unless you have many joins. The following chart will enforce this statement.<br>
![neo4j sql comparison](/paper/images/neo4j_joins.PNG)<br>
(Dhaval Dalal, 2014, slide 19).<br>
As seen in the graph, Neo4j's full potential unleashes when many join-operations are being used as the query execution time stays at a constant low, whereas the execution time for inner joins in MySQL rises exponentially. Another performance aspect is, that Neo4j in its second version can automatically index often used Nodes and get an additional speed advantage out of that.

Overall Neo4j is quite unique, but has high potential in the relational aspects of databases.
It is usefull for complex relational data queries and can be used for many different business fields.
It is still the most popular graph database and some weeknesses can be shortened if you use Neo4j with another NoSQL database.

***
> ## Sources
> - Neo4j Staff (2011) _Intro to Graph Databases._ Retrieved April, 9, 2017, from https://neo4j.com/blog/recap-intro-to-graph-databases-webinar-series-1/
> - Dhaval Dalal (2014). _Neo4j MySql MS-SQL comparison._ Retrieved April, 9, 2017, from https://de.slideshare.net/DhavalDalal/neo4j-my-sqlmssqlcomparisonfinal
