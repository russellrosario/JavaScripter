+++
description = "SQL, NoSQL, Elasticsearch"
title = "Databases"
draft = false
weight = 200
bref="A database is an organized collection of data, generally stored and accessed electronically from a computer system"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section0"><a href="#h-Section0">Databases</a></h3>
  <div class="example">
    <dl>
      <dt>Table</dt>
      <dd>A collection of related data entries consisting of columns and rows in a structured format called a database.</dd>
      <dt>Schema</dt>
      <dd>The skeleton structure that represents the logical view of the entire database. It defines the constraints on the data and relations to other tables.</dd>
      <dt>Primary key</dt>
      <dd>A field in a table which uniquely identifies each row/record in a database table.</dd>
      <dt>Foreign key</dt>
      <dd>A field in a table used to link it to another table.</dd>
      <dt>Database index</dt>
      <dd>A copy of selected columns of data from a table that can be searched very efficiently and includes a direct link to the complete row of data from the original table.</dd>
      <dt>Database normalization<dt>
      <dd>A horizontal partition of data in a database. Each shards is held on a separate database server instance to efficiently spread load.</dd>
      <dt>Database sharding<dt>
      <dd>A vertical partition of data where columns of a table are moved to their own table and replaced with a foreign key.</dd>
      <dt>Master/Slave model<dt>
      <dd>A single Master server for all write operations, and one or many additional Slave servers that provide read-only operations for increasing overall performance. This approach has a write capacity bottleneck and replication is not always in real-time.</dd>
      <dt>ACID<dt>
      <dd>A set of properties of database transactions intended to guarantee validity even in the event of errors, power failures, etc. <b>Atomicity</b> guarantees that each transaction is treated as a single "unit", which either succeeds completely, or fails completely. <b>Consistency</b> ensures that a transaction can only bring the database from one valid state to another. <b>Isolation</b> ensures that concurrent execution of transactions leaves the database in the same state that would have been obtained if the transactions were executed sequentially. <b>Durability</b> guarantees that once a transaction has been committed, it will remain committed even in the case of a system failure.</dd>
    </dl>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.org/img/backend/database_types.jpg">
    </div>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">SQL</a></h3>
  <div class="example">
  <p>SQL (Structured Query Language) lets you access and manipulate relational databases. </p>
    <dl>
      <dt>Commands</dt>
      <dd>
```
SELECT - extracts data from a database
UPDATE - updates data in a database
DELETE - deletes data from a database
INSERT INTO - inserts new data into a database
CREATE DATABASE - creates a new database
ALTER DATABASE - modifies a database
CREATE TABLE - creates a new table
ALTER TABLE - modifies a table
DROP TABLE - deletes a table
CREATE INDEX - creates an index (search key)
DROP INDEX - deletes an index
```

</dd><br/>
      <dt>Queries</dt>
      <dd>
```
SELECT [columns]
FROM [table]
WHERE [comparison predicate on rows]
GROUP BY [columns]
HAVING [comparison predicate on groups]
ORDER BY [columns]
```
</dd>
<dt><dt>Subqueries</dt>
<dd>Queries can be nested so that the results of one query can be used in another query via a relational operator or aggregation function. Joins and other table operations provide faster alternatives.</dd>

<dt>Other Keywords</dt>
<dd>The DISTINCT keyword eliminates duplicate data.<br/>
The LIMIT clause specifies the number of records to return<br/>
The COUNT() function returns the number of rows that matches a specified criteria.<br/>
The AVG() function returns the average value of a numeric column.<br/>
The SUM() function returns the total sum of a numeric column.<br/>
The UNION operator is used to combine multiple similar schema result-sets.</dd><br/>

<dt>Operators</dt>
<dd>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.org/img/backend/sql_operators.png">
    </div>
    </dd>
      <dt>Joins</dt>
      <dd>A JOIN clause is used to combine rows from two or more tables, based on a related column between them.</dd>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.org/img/backend/sql_joins.png">
    </div>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section2"><a href="#h-Section2">SQL vs NoSQL</a></h3>
  <div class="example">
    <dl>
      <dt>NoSQL</dt>
      <dd>Provides a mechanism for storage and retrieval of data that is modeled in means other than the tabular relations used in relational databases. NoSQL systems are also sometimes called "Not only SQL" to emphasize that they may support SQL-like query languages, or sit alongside SQL database in a polyglot persistence architecture.</dd><br/>
      <dt>Why NoSQL?</dt>
      <dd>Simplicity of design, simpler "horizontal" scaling to clusters of machines (which is a problem for relational databases), and finer control over availability. The data structures used by NoSQL databases (e.g. key-value, wide column, graph, or document) are different from those used by default in relational databases, making some operations faster in NoSQL. Sometimes the data structures used by NoSQL databases are also viewed as "more flexible" than relational database tables due to not having to adhere to previously defined schemas.</dd>
    </dl>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.org/img/backend/sql_comparison.png">
    </div>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section4"><a href="#h-Section4">Elasticsearch</a></h3>
  <div class="example">
  <p>A search engine that provides a distributed, multitenant-capable full-text search engine with an HTTP web interface and schema-free JSON documents. Elasticsearch supports real-time GET requests, which makes it suitable as a NoSQL datastore, but it lacks distributed transactions.</p>
    <dl>
      <dt>Features</dt>
      <dd>Elasticsearch is distributed, which means that indices can be divided into shards and each shard can have zero or more replicas. .[5] Related data is often stored in the same index, which consists of one or more primary shards, and zero or more replica shards. Once an index has been created, the number of primary shards cannot be changed. Elasticsearch is developed alongside a data-collection and log-parsing engine called Logstash, and an analytics and visualisation platform called Kibana. The three products are designed for use as an integrated solution, referred to as the "Elastic Stack".</dd>
      <dt>Terminology</dt>
      <dd>An <b>index</b> is like a ‘database’ in a relational database. It has a <b>mapping</b> which is the equivalent of a schema. A <b>document</b> is the equivalent of database record which is serialized as a JSON object.</dd>
      <dt>Cluster</dt>
      <dd>A collection of one or more nodes (servers) that together holds your entire data and provides federated indexing and search capabilities across all nodes. Each node hosts one or more shards, and acts as a coordinator to automatically delegate operations to the correct shard(s). </dd>
      <dt>Shards</dt>
      <dd>An index is split into shards. Documents are hashed to a particular shard. Each shard can be on a different node in a cluster. Follows the master/slave pattern with primary and replica shards. Primary shards are expensive so you do not want to overallocate too much. However, increasing the number of primary shards is a diffiult task that requires reindexing. Replica shards can be increased anytime.</dd>
      <dt>Analyzer</dt>
      <dd>Elasticsearch ships with a wide range of built-in analyzers, which can be used in any index mapping without further configuration. An example an analyzer would be autocomplete. Modifying these analyzers after they have already been created requires reindexing the data.</dd>
      <dt>Aggregations</dt>
      <dd>Collects all the data selected by the search query in order to build complex summaries of the data. Averages, moving averages, histograms, etc.</dd>
      <dt>Full text queries</dt>
      <dd>Includes fuzzy matching and proximity queries.</dd>
      <dt>Elastic Stack</dt>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.org/img/backend/elk.png">
    </div>
      <dt>Technical notes</dt>
      <dd>Use scripts to import CSV directly into Elasticsearch. Or use Logstash to import, parse, and transform data from various sources (Kafka, Apache Spark, Hadoop, MySQL, S3, etc). Logstash then exports into Elasticsearch. Logstash can scale across many nodes and guarantees at-least-once delivery. </dd>
      <dt>Hardware requirements</dt>
      <dd>RAM is the bottleneck, not CPU. Set the heap size to 32GB or half of the available system RAM for Elasticsearch. The remaining will be used for Lucene/OS to cache. Use an SSD with deadline or noop i/o scheduler for improved I/O latency. Redundancy is not important for file storage since the clusters are already redundant.</dd><br/>
     </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>