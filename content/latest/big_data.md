+++
description = "Hadoop, Apache Spark, data streams"
title = "Big data"
draft = false
weight = 300
bref="Big data is a term used to refer to data sets that are too large or complex for traditional data-processing application software to adequately deal with"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">Hadoop</a></h3>
  <div class="example">
    <dl>
      <dt>Use cases</dt>
      <dd>
      <ul>
      <li>Techniques for analyzing data, such as A/B testing, machine learning and natural language processing</li>
      <li>Big data technologies, like business intelligence, cloud computing and databases</li>
      <li>Visualization, such as charts, graphs and other displays of the data</li>
      </ul>
      <dt>Architecture</dt>
      <dd><b>Hadoop</b> uses <ins>Hadoop Distributed File System (HDFS)</ins>. HDFS is used to scale a single cluster to hundreds (and even thousands) of nodes. It is a distributed and highly fault-taolerant file system that handles large data sets running on commodity hardware. Spark initially reads from a file on HDFS, S3, or another filestore, into an established mechanism called the SparkContext. Out of that context, <b>Apache Spark</b> creates a structure called a <ins>DataFrame</ins> (an extension of the Resilient Distributed Dataset RDD with named columns), to represent an immutable collection of elements that can be operated on in parallel.</dd><br/>
      <dd>
      Hadoop uses <ins>YARN</ins> to split up the functionalities of resource management and job scheduling/monitoring into separate daemons. The <ins>Resource Manager</ins> accepts job submissions and allocates resources for the first container. The <ins>Node Manager</ins> is the per-machine framework agent responsible for monitoring container usage and reporting it back to the Resource Manager. The per-application <ins>Application Master</ins> is tasked with negotiating resources from the ResourceManager and working with the NodeManager(s) to execute and monitor the tasks.
      <div style="text-align:center" width="85%">
      <img alt="Image" src="https://www.javascripter.co/img/latest/yarn.gif">
    </div>
      <dt>Spark vs Hadoop MapReduce</dd>
      <dd>With MapReduce, queries are split and distributed across parallel nodes and processed in parallel (the Map step). The results are then gathered and delivered (the Reduce step). Apache Spark was developed in response to limitations in the MapReduce paradigm, as it adds the ability to set up many operations (not just map followed by reduce). In addition, Spark computations are carried out in memory and stored there, until the user actively persists them, whereas Hadoop MapReduce writes to a disk, making it up to 100 times slower. Spark also creates a <b>Directed Acyclic Graph (DAG)</b>, to visualize the order of operations and the relationship between the operations in the DAG. DAGs enable optimizations between steps allowing for it to be up to 10 times faster on disk than Hadoop. However, the volume of data processed also differs: Hadoop MapReduce is able to work with far larger data sets than Spark and is the more economical solution when speed is not critical.</dd>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/dag.png">
    </div>
      <dt></dt>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section3"><a href="#h-Section3">Streams</a></h3>
  <div class="example">
    <dl>
      <dt>Kinesis, pubsub, batch processing, idempotency</dt>
      <dd>A stream is a sequence of data elements made available over time. A stream can be thought of as items on a conveyor belt being processed one at a time rather than in large batches. Streams are processed differently from batch data – normal functions cannot operate on streams as a whole, as they have potentially unlimited data.</dd>
    </dl>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/kinesis.png">
    </div>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>
