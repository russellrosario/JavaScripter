+++
description = "Ethereum, smart contracts, Solidity"
title = "Blockchain"
draft = false
weight = 300
bref="Blockchain is a growing list of records, called blocks, which are linked using cryptography"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">Blockchain analogy in &lt; 100 words</a></h3>
  <div class="example">
    <p>You and your neighbors (<b>"nodes"</b>) have a spreadsheet of transactions (a "<b>ledger</b>"). Public accountants ("<b>miners</b>") have the same spreadsheet (it’s "<b>distributed</b>"). When any neighbor makes a new transaction, every accountant is notified by email. The accountants verify transactions 24/7. Every hour, each accountant submits totals in a new tab (a "<b>block</b>") and their calculations are provided ("<b>Proof of Work</b>"). If the majority of accountants agree, everyone updates their workbook ("<b>blockchain</b>") and the first to report it accurately gets their salary ( "<b>mining reward</b>"). The accountants use Excel to open spreadsheets, which Microsoft (<b>"developers"</b>) updates every year.</p>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section2"><a href="#h-Section2">When to use blockchain?</a></h3>
  <div class="example">
  <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.org/img/latest/why_blockchain.png">
    </div>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section3"><a href="#h-Section3">Proof of work/stake</a></h3>
  <div class="example">
    <p>Similar to Bitcoin, miners are tasked with solving a complex mathematical problem in order to successfully “mine” a block. Any computational problem that requires orders of magnitude more resources to solve algorithmically than it takes to verify the solution is a good candidate for proof of work (factorization of the product of two large prime numbers). In order to discourage centralisation due to the use of specialised hardware, as has occurred in the Bitcoin network, Ethereum chose a memory-hard computational problem which makes Ethereum’s Proof of Work ASIC-resistant. </p>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.org/img/latest/proof.png" width="70%">
    </div>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>


<h3 class="section-head" id="h-Section4"><a href="#h-Section4">Ethereum</a></h3>
  <div class="example">
  <dl>
    <dt>Ethereum</dt>
    <dd> is a prograddmmable blockchain. Rather than give users a set of pre-defined operations (e.g. bitcoin transactions), Ethereum allows users to create their own operations of any complexity they wish. In this way, it serves as a platform for many different types of decentralized blockchain applications, including but not limited to cryptocurrencies. Exchanges of any complexity could be carried out automatically and reliably using code running on Ethereum. Whereas the <b>Bitcoin</b> blockchain was purely a list of transactions, Ethereum’s basic unit is the account. The Ethereum blockchain tracks the state of every account, and all state transitions on the Ethereum blockchain are transfers of value and information between accounts. There are two types of accounts:
      <ul>
      <li>Externally Owned Accounts (EOAs), which are controlled by private keys</li>
      <li>Contract Accounts, which are controlled by their contract code and can only be “activated” by an EOA</li>
      </ul>
      </dd>
    <dt>EVM</dt>
      <dd>At the heart of it is the Ethereum Virtual Machine (“EVM”), which can execute code of arbitrary algorithmic complexity.  Ethereum is “Turing complete” and includes a peer-to-peer network protocol. Each and every node of the network runs the EVM and executes the same instructions in order to maintain consensus across the blockchain. Decentralized consensus gives Ethereum extreme levels of fault tolerance, ensures zero downtime, and makes data stored on the blockchain forever unchangeable and censorship-resistant. Users must pay transaction fees to the nodes that validate the network. This protects the Ethereum blockchain from frivolous or malicious computational tasks, like DDoS attacks or infinite loops. The sender of a transaction must pay for each step of the “program” they activated, including computation and memory storage.</dd><br/>
  </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>


<h3 class="section-head" id="h-Section5"><a href="#h-Section5">Solidity</a></h3>
  <div class="example">
  <p>A language similar to JavaScript which is used for developing Ethereum smart contracts.</p>
  <dl>
    <dt>Smart Contract</dt>
      <dd>A smart contract is a computer protocol intended to digitally facilitate, verify, or enforce the negotiation or performance of a contract. Smart contracts allow the performance of credible transactions without third parties. These transactions are trackable and irreversible. The aim of smart contracts is to provide security that is superior to traditional contract law and to reduce other transaction costs associated with contracting.</dd><br/>
      <dt>Flaws with Ethereum contracts</dt>
      <dd>
      <ul>
      <li>Ambiguities and easy-but-insecure constructs</li>
      <li>Compiler bugs</li>
      <li>Ethereum Virtual Machine bugs</li>
      <li>Attacks on the blockchain network</li>
      <li>The immutability of bugs</li>
      <li>No central source documenting known vulnerabilities</li>
      </ul>
      </dd><br/>
      <dt>Development Tools</dt>
      <dd><ul>
      <li><b>Truffle</b> is a tool for compiling Solidity contracts into EVM bytecode and deploying them to Ethereum networks. Also creates <ins>ABI</ins> interface for interacting with contract.</li>
      <li><b>Web3</b> is a library used by JavaScript apps for programmatic access to contracts deployed on the Ethereum network.</li>
      <li><b>MetaMask</b> is a chrome extension users must have in their browser to transact with Ethereum applications on the web.</li>
      </ul>
      <p>To get started with Solidity, you can use [Remix](https://remix.ethereum.org/), which is an
browser-based IDE. Here are some example contracts:

1. [Voting](https://solidity.readthedocs.io/en/v0.4.24/solidity-by-example.html#voting)
2. [Blind Auction](https://solidity.readthedocs.io/en/v0.4.24/solidity-by-example.html#blind-auction)
3. [Safe remote purchase](https://solidity.readthedocs.io/en/v0.4.24/solidity-by-example.html#safe-remote-purchase)
4. [Micropayment Channel](https://solidity.readthedocs.io/en/v0.4.24/solidity-by-example.html#micropayment-channel)</p>
      </dd><br/>
      <dt>Solidity vs JavaScript</dd>
      <dd>
      <ul>
      <li><b>Version Pragma</b> - Source files can (and should) be annotated with a version pragma to reject being compiled with future compiler versions that might introduce incompatible changes. </li>
      <li><b>Static typing</b> - Argument and variable datatypes need to be declared</li>
      <li><b>New types</b>
      <ul>
      <li>Address - holds a 20 byte value (size of an Ethereum address) and serve as a base for all contracts.</li>
      <li>Function modifiers - automatically check a condition prior to executing the function</li>
      <li>Events - for interacting with EVM</li>
      <li>Structs - custom defined types that can group several variables</li>
      <li>Enums - sequential set of integer values</li>
      <li>Mappings - hash tables which consist of key types and corresponding value type pairs</li>
      <li>Time units - Suffixes like seconds, minutes, hours, days, weeks and years after literal numbers can be used to convert between units of time where seconds are the base unit</li>
      </ul></li>
      <li><b>Data location</b> - Every complex type, i.e. arrays and structs, has an additional annotation, the “data location”, about whether it is stored in memory (which is not persisting) or in storage (where the state variables are held). </li>
      <li><b>Gas</b> - each transaction is charged with a certain amount of Ether, whose purpose is to limit the amount of work that is needed to execute the transaction and to pay for this execution. </li>
      </ul>
      </dd>
      </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>