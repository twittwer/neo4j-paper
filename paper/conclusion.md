# Conclusion

<!--- 
- no joins needed to achive relationships
- similar structure to other document based dbs => parallel/synced/hybrid usage possible (mongodb)
- CAP => CA ( relation oriented -> many side effects, complex queries )
- used by Wallmart (real-time recommandation), Ebay (logistics), LinkedIn (Social Network), TomTom (Geo Routing), !Facebook
- manly relational analytics -> not performant until you have many joins (https://de.slideshare.net/DhavalDalal/neo4j-my-sqlmssqlcomparisonfinal p.19)
- auto index popular nodes by time (http://addisonlee.azurewebsites.net/neo4j-vs-mysql-vs-mongodb/)

=> unique and awesome 
-->

Graph databases, and therefore also Neo4j, don't need joins to achieve relationships, since they are already first-class citizens. This has a huge impact on performance, since join-operations are very expensive.
As Neo4j holds its data as Json it has a similiar structure to document based databases and could therefore be used together. 

In the CAP-theorem Neo4j stands between C and A and is therefore not partition tolerant. Since Neo4j is relationship-oriented trying to achieve partition tolerance can cause many side effects and need complex queries.
Neo4j is used by companies such as Walmart for real-time recommendations, Ebac for logistics, LinkedIn as a Social Network and TomTom for GeoRouting. It is however not used by Facebook, which "they should" as told by the Neo4j staff.<br>
<!---
Kein richtiges Zitat, wie einbinden?
-->
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Neo4j Staff (2011) *Intro to Graph Databases*. https://neo4j.com/blog/recap-intro-to-graph-databases-webinar-series-1/
Neo4j is mainly used for relational analytics and is hence not efficient unless you have many joins. The following chart will enforce this statement.<br>
![neo4j sql comparison](/paper/images/neo4j_joins.PNG)<br>
Dhaval Dalal (2014). Neo4j MySql MS-SQL comparison [Graph & Table]. https://de.slideshare.net/DhavalDalal/neo4j-my-sqlmssqlcomparisonfinal (p. 19).<br>
As seen in the graph, Neo4j's full potential unleashes when many join-operations are being used as the query execution time stays at a constant low, whereas the execution time for inner joins in MySQL rises exponentially.

Overall Neo4j is quite unique, but has high potential in the relational aspects of databases.
