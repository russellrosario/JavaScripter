+++
description = "Hadoop, Spark, Streams, Ethereum"
title = "Big data & Blockchain"
draft = false
weight = 300
bref="Big data is a term used to refer to data sets that are too large or complex for traditional data-processing application software to adequately deal with. Blockchain is a growing list of records, called blocks, which are linked using cryptography"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">Big Data</a></h3>
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
    </div><br/>
      <dt>Spark vs Hadoop MapReduce</dd>
      <dd>With MapReduce, queries are split and distributed across parallel nodes and processed in parallel (the Map step). The results are then gathered and delivered (the Reduce step). Apache Spark was developed in response to limitations in the MapReduce paradigm, as it adds the ability to set up many operations (not just map followed by reduce). In addition, Spark computations are carried out in memory and stored there, until the user actively persists them, whereas Hadoop MapReduce writes to a disk, making it up to 100 times slower. Spark also creates a <b>Directed Acyclic Graph (DAG)</b>, to visualize the order of operations and the relationship between the operations in the DAG. DAGs enable optimizations between steps allowing for it to be up to 10 times faster on disk than Hadoop. However, the volume of data processed also differs: Hadoop MapReduce is able to work with far larger data sets than Spark and is the more economical solution when speed is not critical.</dd>
    <div style="text-align:center" width="75%">
      <img alt="Image" src="https://www.javascripter.co/img/latest/dag.png">
    </div>
    <figcaption style="text-align:center">
    Directed Acyclic Graph
    </figcaption>
      <dt></dt>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section2"><a href="#h-Section2">Streams</a></h3>
  <div class="example">
    <dl>
    <dt>Uses</dt>
    <dd>
      Services like AWS Kinesis and Kafka are designed for large scale data ingestion and processing, with the ability to maximize write throughput for large volumes of data. Typical data streams include log files, e-commerce analytics, in-game player activity, information from social networks, financial trading floors, or geospatial services, and telemetry from connected devices or instrumentation in data centers.
    </dd><br/>
      <dt>Pubsub</dt>
      <dd>A stream is a continuous inbound flow of messages. The messages themselves are encapsulated (individual) and received one at a time in quick succession. The workflow includes one or more message producers and any number of message consumers. This is commonly known as publish/subscribe or “pubsub”. When a message is published, the subscribers receive it nearly instantaneously.
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/pubsub.png">
    </div><br/>
      <dt>Processing considerations</dt>
      <dd><b>Batch processing</b> - Streams are processed differently from batch data – normal functions cannot operate on streams as a whole, as they have potentially unlimited data.</dd>
      <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/batch.jpg">
    </div><br/>
      <dd><b>Idempotence</b> - an idempotent operation is one that has no additional effect if it is called more than once with the same input parameters. Stream services usually provide "at least once" delivery to handle failed operations. This means that there should be some sort of "rollback" for mid-operation failure.</dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section3"><a href="#h-Section3">Blockchain</a></h3>
  <div class="example">
    <dl>
      <dt>Blockchain analogy in &lt; 100 words</dt>
      <dd>You and your neighbors (<b>"nodes"</b>) have a spreadsheet of transactions (a "<b>ledger</b>"). Public accountants ("<b>miners</b>") have the same spreadsheet (it’s "<b>distributed</b>"). When any neighbor makes a new transaction, every accountant is notified by email. The accountants verify transactions 24/7. Every hour, each accountant submits totals in a new tab (a "<b>block</b>") and their calculations are provided ("<b>Proof of Work</b>"). If the majority of accountants agree, everyone updates their workbook ("<b>blockchain</b>") and the first to report it accurately gets their salary ( "<b>mining reward</b>"). The accountants use Excel to open spreadsheets, which Microsoft (<b>"developers"</b>) updates every year.
 </dd><br/>
    <dt>When to use blockchain?</dt>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/latest/why_blockchain.png">
    </div><br/>
      <dt>Ethereum</dt>
      <dd>Ethereum is a programmable blockchain. Rather than give users a set of pre-defined operations (e.g. bitcoin transactions), Ethereum allows users to create their own operations of any complexity they wish. In this way, it serves as a platform for many different types of decentralized blockchain applications, including but not limited to cryptocurrencies. Exchanges of any complexity could be carried out automatically and reliably using code running on Ethereum. Whereas the <b>Bitcoin</b> blockchain was purely a list of transactions, Ethereum’s basic unit is the account. The Ethereum blockchain tracks the state of every account, and all state transitions on the Ethereum blockchain are transfers of value and information between accounts. There are two types of accounts:
      <ul>
      <li>Externally Owned Accounts (EOAs), which are controlled by private keys</li>
      <li>Contract Accounts, which are controlled by their contract code and can only be “activated” by an EOA</li>
      </ul>
</dd>
      <dt>EVM</dt>
      <dd>At the heart of it is the Ethereum Virtual Machine (“EVM”), which can execute code of arbitrary algorithmic complexity.  Ethereum is “Turing complete” and includes a peer-to-peer network protocol. Each and every node of the network runs the EVM and executes the same instructions in order to maintain consensus across the blockchain. Decentralized consensus gives Ethereum extreme levels of fault tolerance, ensures zero downtime, and makes data stored on the blockchain forever unchangeable and censorship-resistant. Users must pay transaction fees to the nodes that validate the network. This protects the Ethereum blockchain from frivolous or malicious computational tasks, like DDoS attacks or infinite loops. The sender of a transaction must pay for each step of the “program” they activated, including computation and memory storage.</dd><br/>
      <dt>Proof of work</dt>
      <dd>Similar to Bitcoin, miners are tasked with solving a complex mathematical problem in order to successfully “mine” a block. Any computational problem that requires orders of magnitude more resources to solve algorithmically than it takes to verify the solution is a good candidate for proof of work (factorization of the product of two large prime numbers). In order to discourage centralisation due to the use of specialised hardware, as has occurred in the Bitcoin network, Ethereum chose a memory-hard computational problem which makes Ethereum’s Proof of Work ASIC-resistant. </dd><br/>
      <dt>Smart Contract</dt>
      <dd>A smart contract is a computer protocol intended to digitally facilitate, verify, or enforce the negotiation or performance of a contract. Smart contracts allow the performance of credible transactions without third parties. These transactions are trackable and irreversible. The aim of smart contracts is to provide security that is superior to traditional contract law and to reduce other transaction costs associated with contracting. Issues in Ethereum smart contracts include ambiguities and easy-but-insecure constructs in its contract language Solidity, compiler bugs, Ethereum Virtual Machine bugs, attacks on the blockchain network, the immutability of bugs and that there is no central source documenting known vulnerabilities, attacks and problematic constructs. </dd><br/>
    <div style="text-align:center" width="85%">
      <img alt="Image" src="https://www.javascripter.co/img/latest/smart_contract.png">
    </div><br/>
    <dt>Development on Ethereum</dt>
      <dd><b>Solidity</b> is a language similar to JavaScript which is used for developing Ethereum contracts. <b>Truffle</b> is a tool for compiling Solidity contracts into EVM bytecode and deploying them to Ethereum networks. <b>Web3</b> is a library used by JavaScript apps for programmatic access to contracts deployed on the Ethereum network. It makes use of the <b>ABI</b> (interface) created when Truffle compiled the contract. <b>MetaMask</b> is a chrome extension users must have in their browser to transact with Ethereum applications on the web.</dd><br/>
      <dd>Use <a href="https://remix.ethereum.org/">Remix</a>, a Solidity IDE, to test code and play around with Ethereum contracts.</dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>