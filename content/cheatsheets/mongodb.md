+++
description = "MongoDB and Mongoose NoSQL methods"
title = "MongoDB"
date = "2017-04-10T16:43:08+01:00"
draft = false
weight = 200
bref="MongoDB is a free and open-source cross-platform document-oriented database program. Classified as a NoSQL database program, MongoDB uses JSON-like documents with schemata"
toc = true
script = 'animation'
+++

# MongoDB and Mongoose

[SQL to MongoDB Mapping Chart](http://docs.mongodb.org/manual/reference/sql-comparison/#sql-to-mongodb-mapping-chart)

<div class="section" id="sql-to-mongodb-mapping-chart">
<p>In addition to the charts that follow, you might want to consider the
<a class="reference internal" href="../../faq/"><em>Frequently Asked Questions</em></a> section for a selection of common questions about MongoDB.</p>
<div class="section" id="executables">

<h2>Terminology and Concepts<a class="headerlink" href="#terminology-and-concepts" title="Permalink to this headline">¶</a></h2>
<p>The following table presents the various SQL terminology and concepts
and the corresponding MongoDB terminology and concepts.</p>
<table border="1" class="docutils">
<colgroup>
<col width="51%">
<col width="49%">
</colgroup>
<thead valign="bottom">
<tr class="row-odd"><th class="head">SQL Terms/Concepts</th>
<th class="head">MongoDB Terms/Concepts</th>
</tr>
</thead>
<tbody valign="top">
<tr class="row-even"><td>database</td>
<td><a class="reference internal" href="../glossary/#term-database"><em class="xref std std-term">database</em></a></td>
</tr>
<tr class="row-odd"><td>table</td>
<td><a class="reference internal" href="../glossary/#term-collection"><em class="xref std std-term">collection</em></a></td>
</tr>
<tr class="row-even"><td>row</td>
<td><a class="reference internal" href="../glossary/#term-document"><em class="xref std std-term">document</em></a> or <a class="reference internal" href="../glossary/#term-bson"><em class="xref std std-term">BSON</em></a> document</td>
</tr>
<tr class="row-odd"><td>column</td>
<td><a class="reference internal" href="../glossary/#term-field"><em class="xref std std-term">field</em></a></td>
</tr>
<tr class="row-even"><td>index</td>
<td><a class="reference internal" href="../glossary/#term-index"><em class="xref std std-term">index</em></a></td>
</tr>
<tr class="row-odd"><td>table joins</td>
<td>embedded documents and linking</td>
</tr>
<tr class="row-even"><td><p class="first">primary key</p>
<p class="last">Specify any unique column or column combination as primary
key.</p>
</td>
<td><p class="first"><a class="reference internal" href="../glossary/#term-primary-key"><em class="xref std std-term">primary key</em></a></p>
<p class="last">In MongoDB, the primary key is automatically set to the
<a class="reference internal" href="../glossary/#term-id"><em class="xref std std-term">_id</em></a> field.</p>
</td>
</tr>
<tr class="row-odd"><td>aggregation (e.g. group by)</td>
<td><p class="first">aggregation framework</p>
<p class="last">See the <a class="reference internal" href="../sql-aggregation-comparison/"><em>SQL to Aggregation Framework Mapping Chart</em></a>.</p>
</td>
</tr>
</tbody>
</table>
</div>
<div class="section" id="examples">
<h2>Examples<a class="headerlink" href="#examples" title="Permalink to this headline">¶</a></h2>
<p>The following table presents the various SQL statements and the
corresponding MongoDB statements. The examples in the table assume the
following conditions:</p>
<ul>
<li><p class="first">The SQL examples assume a table named <tt class="docutils literal"><span class="pre">users</span></tt>.</p>
</li>
<li><p class="first">The MongoDB examples assume a collection named <tt class="docutils literal"><span class="pre">users</span></tt> that contain
documents of the following prototype:</p>
<div class="highlight-javascript"><div class="highlight"><pre><span class="p">{</span>
  <span class="nx">_id</span><span class="o">:</span> <span class="nx">ObjectID</span><span class="p">(</span><span class="s2">"509a8fb2f3f4948bd2f983a0"</span><span class="p">),</span>
  <span class="nx">user_id</span><span class="o">:</span> <span class="s2">"abc123"</span><span class="p">,</span>
  <span class="nx">age</span><span class="o">:</span> <span class="mi">55</span><span class="p">,</span>
  <span class="nx">status</span><span class="o">:</span> <span class="s1">'A'</span>
<span class="p">}</span>
</pre></div>
</div>
</li>
</ul>
<div class="section" id="create-and-alter">
<h3>Create and Alter<a class="headerlink" href="#create-and-alter" title="Permalink to this headline">¶</a></h3>
<p>The following table presents the various SQL statements related to
table-level actions and the corresponding MongoDB statements.</p>
<table border="1" class="docutils">
<colgroup>
<col width="22%">
<col width="39%">
<col width="39%">
</colgroup>
<thead valign="bottom">
<tr class="row-odd"><th class="head">SQL Schema Statements</th>
<th class="head">MongoDB Schema Statements</th>
<th class="head">Reference</th>
</tr>
</thead>
<tbody valign="top">
<tr class="row-even"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">CREATE</span> <span class="k">TABLE</span> <span class="n">users</span> <span class="p">(</span>
    <span class="n">id</span> <span class="n">MEDIUMINT</span> <span class="k">NOT</span> <span class="k">NULL</span>
        <span class="n">AUTO_INCREMENT</span><span class="p">,</span>
    <span class="n">user_id</span> <span class="nb">Varchar</span><span class="p">(</span><span class="mi">30</span><span class="p">),</span>
    <span class="n">age</span> <span class="nb">Number</span><span class="p">,</span>
    <span class="n">status</span> <span class="nb">char</span><span class="p">(</span><span class="mi">1</span><span class="p">),</span>
    <span class="k">PRIMARY</span> <span class="k">KEY</span> <span class="p">(</span><span class="n">id</span><span class="p">)</span>
<span class="p">)</span>
</pre></div>
</div>
</td>
<td><p class="first">Implicitly created on first <a class="reference internal" href="../method/db.collection.insert/#db.collection.insert" title="db.collection.insert"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">insert</span></tt></a> operation. The primary key <tt class="docutils literal"><span class="pre">_id</span></tt> is
automatically added if <tt class="docutils literal"><span class="pre">_id</span></tt> field is not specified.</p>
<div class="highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">insert</span><span class="p">(</span> <span class="p">{</span>
</span><span class="hll">    <span class="nx">user_id</span><span class="o">:</span> <span class="s2">"abc123"</span><span class="p">,</span>
</span><span class="hll">    <span class="nx">age</span><span class="o">:</span> <span class="mi">55</span><span class="p">,</span>
</span><span class="hll">    <span class="nx">status</span><span class="o">:</span> <span class="s2">"A"</span>
</span><span class="hll"> <span class="p">}</span> <span class="p">)</span>
</span></pre></div>
</div>
<p>However, you can also explicitly create a collection:</p>
<div class="last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">createCollection</span><span class="p">(</span><span class="s2">"users"</span><span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See
<a class="reference internal" href="../method/db.collection.insert/#db.collection.insert" title="db.collection.insert"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">insert()</span></tt></a> and
<a class="reference internal" href="../method/db.createCollection/#db.createCollection" title="db.createCollection"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">createCollection()</span></tt></a>
for more information.</td>
</tr>
<tr class="row-odd"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">ALTER</span> <span class="k">TABLE</span> <span class="n">users</span>
<span class="k">ADD</span> <span class="n">join_date</span> <span class="n">DATETIME</span>
</pre></div>
</div>
</td>
<td>Collections do not describe or enforce the structure of the
constituent documents. See the <a class="reference external" href="http://www.mongodb.org/display/DOCS/Schema+Design">Schema Design</a> wiki page for more information.</td>
<td>See <a class="reference internal" href="../method/db.collection.update/#db.collection.update" title="db.collection.update"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">update()</span></tt></a> and
<a class="reference internal" href="../operators/#_S_set" title="$set"><tt class="xref mongodb mongodb-operator docutils literal"><span class="pre">$set</span></tt></a> for more information on changing the structure
of documents in a collection.</td>
</tr>
<tr class="row-even"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">ALTER</span> <span class="k">TABLE</span> <span class="n">users</span>
<span class="k">DROP</span> <span class="k">COLUMN</span> <span class="n">join_date</span>
</pre></div>
</div>
</td>
<td>Collections do not describe or enforce the structure of the
constituent documents. See the <a class="reference external" href="http://www.mongodb.org/display/DOCS/Schema+Design">Schema Design</a> wiki page for more information.</td>
<td>See <a class="reference internal" href="../method/db.collection.update/#db.collection.update" title="db.collection.update"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">update()</span></tt></a> and
<a class="reference internal" href="../operators/#_S_set" title="$set"><tt class="xref mongodb mongodb-operator docutils literal"><span class="pre">$set</span></tt></a> for more information on changing the structure
of documents in a collection.</td>
</tr>
<tr class="row-odd"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">CREATE</span> <span class="k">INDEX</span> <span class="n">idx_user_id_asc</span>
<span class="k">ON</span> <span class="n">users</span><span class="p">(</span><span class="n">user_id</span><span class="p">)</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">ensureIndex</span><span class="p">(</span> <span class="p">{</span> <span class="nx">user_id</span><span class="o">:</span> <span class="mi">1</span> <span class="p">}</span> <span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.ensureIndex/#db.collection.ensureIndex" title="db.collection.ensureIndex"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">ensureIndex()</span></tt></a>
and <a class="reference internal" href="../../core/indexes/"><em>indexes</em></a> for more information.</td>
</tr>
<tr class="row-even"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">CREATE</span> <span class="k">INDEX</span>
       <span class="n">idx_user_id_asc_age_desc</span>
<span class="k">ON</span> <span class="n">users</span><span class="p">(</span><span class="n">user_id</span><span class="p">,</span> <span class="n">age</span> <span class="k">DESC</span><span class="p">)</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">ensureIndex</span><span class="p">(</span> <span class="p">{</span> <span class="nx">user_id</span><span class="o">:</span> <span class="mi">1</span><span class="p">,</span> <span class="nx">age</span><span class="o">:</span> <span class="o">-</span><span class="mi">1</span> <span class="p">}</span> <span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.ensureIndex/#db.collection.ensureIndex" title="db.collection.ensureIndex"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">ensureIndex()</span></tt></a>
and <a class="reference internal" href="../../core/indexes/"><em>indexes</em></a> for more information.</td>
</tr>
<tr class="row-odd"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">DROP</span> <span class="k">TABLE</span> <span class="n">users</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">drop</span><span class="p">()</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.drop/#db.collection.drop" title="db.collection.drop"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">drop()</span></tt></a> for
more information.</td>
</tr>
</tbody>
</table>
</div>
<div class="section" id="insert">
<h3>Insert<a class="headerlink" href="#insert" title="Permalink to this headline">¶</a></h3>
<p>The following table presents the various SQL statements related to
inserting records into tables and the corresponding MongoDB statements.</p>
<table border="1" class="docutils">
<colgroup>
<col width="30%">
<col width="31%">
<col width="39%">
</colgroup>
<thead valign="bottom">
<tr class="row-odd"><th class="head">SQL INSERT Statements</th>
<th class="head">MongoDB insert() Statements</th>
<th class="head">Reference</th>
</tr>
</thead>
<tbody valign="top">
<tr class="row-even"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">INSERT</span> <span class="k">INTO</span> <span class="n">users</span><span class="p">(</span><span class="n">user_id</span><span class="p">,</span>
                  <span class="n">age</span><span class="p">,</span>
                  <span class="n">status</span><span class="p">)</span>
<span class="k">VALUES</span> <span class="p">(</span><span class="ss">"bcd001"</span><span class="p">,</span>
        <span class="mi">45</span><span class="p">,</span>
        <span class="ss">"A"</span><span class="p">)</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">insert</span><span class="p">(</span> <span class="p">{</span>
</span><span class="hll">       <span class="nx">user_id</span><span class="o">:</span> <span class="s2">"bcd001"</span><span class="p">,</span>
</span><span class="hll">       <span class="nx">age</span><span class="o">:</span> <span class="mi">45</span><span class="p">,</span>
</span><span class="hll">       <span class="nx">status</span><span class="o">:</span> <span class="s2">"A"</span>
</span><span class="hll"><span class="p">}</span> <span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.insert/#db.collection.insert" title="db.collection.insert"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">insert()</span></tt></a>
for more information.</td>
</tr>
</tbody>
</table>
</div>
<div class="section" id="select">
<h3>Select<a class="headerlink" href="#select" title="Permalink to this headline">¶</a></h3>
<p>The following table presents the various SQL statements related to
reading records from tables and the corresponding MongoDB statements.</p>
<table border="1" class="docutils">
<colgroup>
<col width="21%">
<col width="42%">
<col width="37%">
</colgroup>
<thead valign="bottom">
<tr class="row-odd"><th class="head">SQL SELECT Statements</th>
<th class="head">MongoDB find() Statements</th>
<th class="head">Reference</th>
</tr>
</thead>
<tbody valign="top">
<tr class="row-even"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="o">*</span>
<span class="k">FROM</span> <span class="n">users</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">()</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>
for more information.</td>
</tr>
<tr class="row-odd"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="n">id</span><span class="p">,</span> <span class="n">user_id</span><span class="p">,</span> <span class="n">status</span>
<span class="k">FROM</span> <span class="n">users</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">(</span>
</span><span class="hll">    <span class="p">{</span> <span class="p">},</span>
</span><span class="hll">    <span class="p">{</span> <span class="nx">user_id</span><span class="o">:</span> <span class="mi">1</span><span class="p">,</span> <span class="nx">status</span><span class="o">:</span> <span class="mi">1</span> <span class="p">}</span>
</span><span class="hll"><span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>
for more information.</td>
</tr>
<tr class="row-even"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="n">user_id</span><span class="p">,</span> <span class="n">status</span>
<span class="k">FROM</span> <span class="n">users</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">(</span>
</span><span class="hll">    <span class="p">{</span> <span class="p">},</span>
</span><span class="hll">    <span class="p">{</span> <span class="nx">user_id</span><span class="o">:</span> <span class="mi">1</span><span class="p">,</span> <span class="nx">status</span><span class="o">:</span> <span class="mi">1</span><span class="p">,</span> <span class="nx">_id</span><span class="o">:</span> <span class="mi">0</span> <span class="p">}</span>
</span><span class="hll"><span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>
for more information.</td>
</tr>
<tr class="row-odd"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="o">*</span>
<span class="k">FROM</span> <span class="n">users</span>
<span class="k">WHERE</span> <span class="n">status</span> <span class="o">=</span> <span class="ss">"A"</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">(</span>
</span><span class="hll">    <span class="p">{</span> <span class="nx">status</span><span class="o">:</span> <span class="s2">"A"</span> <span class="p">}</span>
</span><span class="hll"><span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>
for more information.</td>
</tr>
<tr class="row-even"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="n">user_id</span><span class="p">,</span> <span class="n">status</span>
<span class="k">FROM</span> <span class="n">users</span>
<span class="k">WHERE</span> <span class="n">status</span> <span class="o">=</span> <span class="ss">"A"</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">(</span>
</span><span class="hll">    <span class="p">{</span> <span class="nx">status</span><span class="o">:</span> <span class="s2">"A"</span> <span class="p">},</span>
</span><span class="hll">    <span class="p">{</span> <span class="nx">user_id</span><span class="o">:</span> <span class="mi">1</span><span class="p">,</span> <span class="nx">status</span><span class="o">:</span> <span class="mi">1</span><span class="p">,</span> <span class="nx">_id</span><span class="o">:</span> <span class="mi">0</span> <span class="p">}</span>
</span><span class="p">)</span>
</pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>
for more information.</td>
</tr>
<tr class="row-odd"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="o">*</span>
<span class="k">FROM</span> <span class="n">users</span>
<span class="k">WHERE</span> <span class="n">status</span> <span class="o">!=</span> <span class="ss">"A"</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">(</span>
</span><span class="hll">    <span class="p">{</span> <span class="nx">status</span><span class="o">:</span> <span class="p">{</span> <span class="nx">$ne</span><span class="o">:</span> <span class="s2">"A"</span> <span class="p">}</span> <span class="p">}</span>
</span><span class="hll"><span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>
and <a class="reference internal" href="../operators/#_S_ne" title="$ne"><tt class="xref mongodb mongodb-operator docutils literal"><span class="pre">$ne</span></tt></a> for more information.</td>
</tr>
<tr class="row-even"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="o">*</span>
<span class="k">FROM</span> <span class="n">users</span>
<span class="k">WHERE</span> <span class="n">status</span> <span class="o">=</span> <span class="ss">"A"</span>
<span class="k">AND</span> <span class="n">age</span> <span class="o">=</span> <span class="mi">50</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">(</span>
</span><span class="hll">    <span class="p">{</span> <span class="nx">status</span><span class="o">:</span> <span class="s2">"A"</span><span class="p">,</span>
</span><span class="hll">      <span class="nx">age</span><span class="o">:</span> <span class="mi">50</span> <span class="p">}</span>
</span><span class="hll"><span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>
and <a class="reference internal" href="../operators/#_S_and" title="$and"><tt class="xref mongodb mongodb-operator docutils literal"><span class="pre">$and</span></tt></a> for more information.</td>
</tr>
<tr class="row-odd"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="o">*</span>
<span class="k">FROM</span> <span class="n">users</span>
<span class="k">WHERE</span> <span class="n">status</span> <span class="o">=</span> <span class="ss">"A"</span>
<span class="k">OR</span> <span class="n">age</span> <span class="o">=</span> <span class="mi">50</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">(</span>
</span><span class="hll">    <span class="p">{</span> <span class="nx">$or</span><span class="o">:</span> <span class="p">[</span> <span class="p">{</span> <span class="nx">status</span><span class="o">:</span> <span class="s2">"A"</span> <span class="p">}</span> <span class="p">,</span>
</span><span class="hll">             <span class="p">{</span> <span class="nx">age</span><span class="o">:</span> <span class="mi">50</span> <span class="p">}</span> <span class="p">]</span> <span class="p">}</span>
</span><span class="hll"><span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>
and <a class="reference internal" href="../operators/#_S_or" title="$or"><tt class="xref mongodb mongodb-operator docutils literal"><span class="pre">$or</span></tt></a> for more information.</td>
</tr>
<tr class="row-even"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="o">*</span>
<span class="k">FROM</span> <span class="n">users</span>
<span class="k">WHERE</span> <span class="n">age</span> <span class="o">&gt;</span> <span class="mi">25</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">(</span>
</span><span class="hll">    <span class="p">{</span> <span class="nx">age</span><span class="o">:</span> <span class="p">{</span> <span class="nx">$gt</span><span class="o">:</span> <span class="mi">25</span> <span class="p">}</span> <span class="p">}</span>
</span><span class="hll"><span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>
and <a class="reference internal" href="../operators/#_S_gt" title="$gt"><tt class="xref mongodb mongodb-operator docutils literal"><span class="pre">$gt</span></tt></a> for more information.</td>
</tr>
<tr class="row-odd"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="o">*</span>
<span class="k">FROM</span> <span class="n">users</span>
<span class="k">WHERE</span> <span class="n">age</span> <span class="o">&lt;</span> <span class="mi">25</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">(</span>
</span><span class="hll">   <span class="p">{</span> <span class="nx">age</span><span class="o">:</span> <span class="p">{</span> <span class="nx">$lt</span><span class="o">:</span> <span class="mi">25</span> <span class="p">}</span> <span class="p">}</span>
</span><span class="hll"><span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>
and <a class="reference internal" href="../operators/#_S_lt" title="$lt"><tt class="xref mongodb mongodb-operator docutils literal"><span class="pre">$lt</span></tt></a> for more information.</td>
</tr>
<tr class="row-even"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="o">*</span>
<span class="k">FROM</span> <span class="n">users</span>
<span class="k">WHERE</span> <span class="n">age</span> <span class="o">&gt;</span> <span class="mi">25</span>
<span class="k">AND</span>   <span class="n">age</span> <span class="o">&lt;=</span> <span class="mi">50</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">(</span>
</span><span class="hll">   <span class="p">{</span> <span class="nx">age</span><span class="o">:</span> <span class="p">{</span> <span class="nx">$gt</span><span class="o">:</span> <span class="mi">25</span><span class="p">,</span> <span class="nx">$lte</span><span class="o">:</span> <span class="mi">50</span> <span class="p">}</span> <span class="p">}</span>
</span><span class="hll"><span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>,
<a class="reference internal" href="../operators/#_S_gt" title="$gt"><tt class="xref mongodb mongodb-operator docutils literal"><span class="pre">$gt</span></tt></a>, and <a class="reference internal" href="../operators/#_S_lte" title="$lte"><tt class="xref mongodb mongodb-operator docutils literal"><span class="pre">$lte</span></tt></a> for
more information.</td>
</tr>
<tr class="row-odd"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="o">*</span>
<span class="k">FROM</span> <span class="n">users</span>
<span class="k">WHERE</span> <span class="n">user_id</span> <span class="k">like</span> <span class="ss">"%bc%"</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">(</span>
</span><span class="hll">   <span class="p">{</span> <span class="nx">user_id</span><span class="o">:</span> <span class="sr">/bc/</span> <span class="p">}</span>
</span><span class="hll"><span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>
and <a class="reference internal" href="../operators/#_S_regex" title="$regex"><tt class="xref mongodb mongodb-operator docutils literal"><span class="pre">$regex</span></tt></a> for more information.</td>
</tr>
<tr class="row-even"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="o">*</span>
<span class="k">FROM</span> <span class="n">users</span>
<span class="k">WHERE</span> <span class="n">user_id</span> <span class="k">like</span> <span class="ss">"bc%"</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">(</span>
</span><span class="hll">   <span class="p">{</span> <span class="nx">user_id</span><span class="o">:</span> <span class="sr">/^bc/</span> <span class="p">}</span>
</span><span class="hll"><span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>
and <a class="reference internal" href="../operators/#_S_regex" title="$regex"><tt class="xref mongodb mongodb-operator docutils literal"><span class="pre">$regex</span></tt></a> for more information.</td>
</tr>
<tr class="row-odd"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="o">*</span>
<span class="k">FROM</span> <span class="n">users</span>
<span class="k">WHERE</span> <span class="n">status</span> <span class="o">=</span> <span class="ss">"A"</span>
<span class="k">ORDER</span> <span class="k">BY</span> <span class="n">user_id</span> <span class="k">ASC</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">(</span> <span class="p">{</span> <span class="nx">status</span><span class="o">:</span> <span class="s2">"A"</span> <span class="p">}</span> <span class="p">).</span><span class="nx">sort</span><span class="p">(</span> <span class="p">{</span> <span class="nx">user_id</span><span class="o">:</span> <span class="mi">1</span> <span class="p">}</span> <span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>
and <a class="reference internal" href="../method/cursor.sort/#cursor.sort" title="cursor.sort"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">sort()</span></tt></a>
for more information.</td>
</tr>
<tr class="row-even"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="o">*</span>
<span class="k">FROM</span> <span class="n">users</span>
<span class="k">WHERE</span> <span class="n">status</span> <span class="o">=</span> <span class="ss">"A"</span>
<span class="k">ORDER</span> <span class="k">BY</span> <span class="n">user_id</span> <span class="k">DESC</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">(</span> <span class="p">{</span> <span class="nx">status</span><span class="o">:</span> <span class="s2">"A"</span> <span class="p">}</span> <span class="p">).</span><span class="nx">sort</span><span class="p">(</span> <span class="p">{</span> <span class="nx">user_id</span><span class="o">:</span> <span class="o">-</span><span class="mi">1</span> <span class="p">}</span> <span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>
and <a class="reference internal" href="../method/cursor.sort/#cursor.sort" title="cursor.sort"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">sort()</span></tt></a>
for more information.</td>
</tr>
<tr class="row-odd"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="k">COUNT</span><span class="p">(</span><span class="o">*</span><span class="p">)</span>
<span class="k">FROM</span> <span class="n">users</span>
</pre></div>
</div>
</td>
<td><div class="first highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">count</span><span class="p">()</span>
</span></pre></div>
</div>
<p><em>or</em></p>
<div class="last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">().</span><span class="nx">count</span><span class="p">()</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>
and <a class="reference internal" href="../method/cursor.count/#cursor.count" title="cursor.count"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">count()</span></tt></a> for
more information.</td>
</tr>
<tr class="row-even"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="k">COUNT</span><span class="p">(</span><span class="n">user_id</span><span class="p">)</span>
<span class="k">FROM</span> <span class="n">users</span>
</pre></div>
</div>
</td>
<td><div class="first highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">count</span><span class="p">(</span> <span class="p">{</span> <span class="nx">user_id</span><span class="o">:</span> <span class="p">{</span> <span class="nx">$exists</span><span class="o">:</span> <span class="kc">true</span> <span class="p">}</span> <span class="p">}</span> <span class="p">)</span>
</span></pre></div>
</div>
<p><em>or</em></p>
<div class="last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">(</span> <span class="p">{</span> <span class="nx">user_id</span><span class="o">:</span> <span class="p">{</span> <span class="nx">$exists</span><span class="o">:</span> <span class="kc">true</span> <span class="p">}</span> <span class="p">}</span> <span class="p">).</span><span class="nx">count</span><span class="p">()</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>,
<a class="reference internal" href="../method/cursor.count/#cursor.count" title="cursor.count"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">count()</span></tt></a>, and
<a class="reference internal" href="../operators/#_S_exists" title="$exists"><tt class="xref mongodb mongodb-operator docutils literal"><span class="pre">$exists</span></tt></a> for more information.</td>
</tr>
<tr class="row-odd"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="k">COUNT</span><span class="p">(</span><span class="o">*</span><span class="p">)</span>
<span class="k">FROM</span> <span class="n">users</span>
<span class="k">WHERE</span> <span class="n">age</span> <span class="o">&gt;</span> <span class="mi">30</span>
</pre></div>
</div>
</td>
<td><div class="first highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">count</span><span class="p">(</span> <span class="p">{</span> <span class="nx">age</span><span class="o">:</span> <span class="p">{</span> <span class="nx">$gt</span><span class="o">:</span> <span class="mi">30</span> <span class="p">}</span> <span class="p">}</span> <span class="p">)</span>
</span></pre></div>
</div>
<p><em>or</em></p>
<div class="last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">(</span> <span class="p">{</span> <span class="nx">age</span><span class="o">:</span> <span class="p">{</span> <span class="nx">$gt</span><span class="o">:</span> <span class="mi">30</span> <span class="p">}</span> <span class="p">}</span> <span class="p">).</span><span class="nx">count</span><span class="p">()</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>,
<a class="reference internal" href="../method/cursor.count/#cursor.count" title="cursor.count"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">count()</span></tt></a>, and
<a class="reference internal" href="../operators/#_S_gt" title="$gt"><tt class="xref mongodb mongodb-operator docutils literal"><span class="pre">$gt</span></tt></a> for more information.</td>
</tr>
<tr class="row-even"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="k">DISTINCT</span><span class="p">(</span><span class="n">status</span><span class="p">)</span>
<span class="k">FROM</span> <span class="n">users</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">distinct</span><span class="p">(</span> <span class="s2">"status"</span> <span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>
and <a class="reference internal" href="../method/db.collection.distinct/#db.collection.distinct" title="db.collection.distinct"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">distinct()</span></tt></a>
for more information.</td>
</tr>
<tr class="row-odd"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="o">*</span>
<span class="k">FROM</span> <span class="n">users</span>
<span class="k">LIMIT</span> <span class="mi">1</span>
</pre></div>
</div>
</td>
<td><div class="first highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">findOne</span><span class="p">()</span>
</span></pre></div>
</div>
<p><em>or</em></p>
<div class="last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">().</span><span class="nx">limit</span><span class="p">(</span><span class="mi">1</span><span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>,
<a class="reference internal" href="../method/db.collection.findOne/#db.collection.findOne" title="db.collection.findOne"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">findOne()</span></tt></a>,
and <a class="reference internal" href="../method/cursor.limit/#cursor.limit" title="cursor.limit"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">limit()</span></tt></a>
for more information.</td>
</tr>
<tr class="row-even"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">SELECT</span> <span class="o">*</span>
<span class="k">FROM</span> <span class="n">users</span>
<span class="k">LIMIT</span> <span class="mi">5</span>
<span class="n">SKIP</span> <span class="mi">10</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">().</span><span class="nx">limit</span><span class="p">(</span><span class="mi">5</span><span class="p">).</span><span class="nx">skip</span><span class="p">(</span><span class="mi">10</span><span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>,
<a class="reference internal" href="../method/cursor.limit/#cursor.limit" title="cursor.limit"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">limit()</span></tt></a>, and
<a class="reference internal" href="../method/cursor.skip/#cursor.skip" title="cursor.skip"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">skip()</span></tt></a> for
more information.</td>
</tr>
<tr class="row-odd"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">EXPLAIN</span> <span class="k">SELECT</span> <span class="o">*</span>
<span class="k">FROM</span> <span class="n">users</span>
<span class="k">WHERE</span> <span class="n">status</span> <span class="o">=</span> <span class="ss">"A"</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">find</span><span class="p">(</span> <span class="p">{</span> <span class="nx">status</span><span class="o">:</span> <span class="s2">"A"</span> <span class="p">}</span> <span class="p">).</span><span class="nx">explain</span><span class="p">()</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.find/#db.collection.find" title="db.collection.find"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">find()</span></tt></a>
and <a class="reference internal" href="../method/cursor.explain/#cursor.explain" title="cursor.explain"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">explain()</span></tt></a>
for more information.</td>
</tr>
</tbody>
</table>
</div>
<div class="section" id="update-records">
<h3>Update Records<a class="headerlink" href="#update-records" title="Permalink to this headline">¶</a></h3>
<p>The following table presents the various SQL statements related to
updating existing records in tables and the corresponding MongoDB
statements.</p>
<table border="1" class="docutils">
<colgroup>
<col width="21%">
<col width="32%">
<col width="47%">
</colgroup>
<thead valign="bottom">
<tr class="row-odd"><th class="head">SQL Update Statements</th>
<th class="head">MongoDB update() Statements</th>
<th class="head">Reference</th>
</tr>
</thead>
<tbody valign="top">
<tr class="row-even"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">UPDATE</span> <span class="n">users</span>
<span class="k">SET</span> <span class="n">status</span> <span class="o">=</span> <span class="ss">"C"</span>
<span class="k">WHERE</span> <span class="n">age</span> <span class="o">&gt;</span> <span class="mi">25</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">update</span><span class="p">(</span>
</span><span class="hll">   <span class="p">{</span> <span class="nx">age</span><span class="o">:</span> <span class="p">{</span> <span class="nx">$gt</span><span class="o">:</span> <span class="mi">25</span> <span class="p">}</span> <span class="p">},</span>
</span><span class="hll">   <span class="p">{</span> <span class="nx">$set</span><span class="o">:</span> <span class="p">{</span> <span class="nx">status</span><span class="o">:</span> <span class="s2">"C"</span> <span class="p">}</span> <span class="p">},</span>
</span><span class="hll">   <span class="p">{</span> <span class="nx">multi</span><span class="o">:</span> <span class="kc">true</span> <span class="p">}</span>
</span><span class="hll"><span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.update/#db.collection.update" title="db.collection.update"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">update()</span></tt></a>,
<a class="reference internal" href="../operators/#_S_gt" title="$gt"><tt class="xref mongodb mongodb-operator docutils literal"><span class="pre">$gt</span></tt></a>, and <a class="reference internal" href="../operators/#_S_set" title="$set"><tt class="xref mongodb mongodb-operator docutils literal"><span class="pre">$set</span></tt></a> for more
information.</td>
</tr>
<tr class="row-odd"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">UPDATE</span> <span class="n">users</span>
<span class="k">SET</span> <span class="n">age</span> <span class="o">=</span> <span class="n">age</span> <span class="o">+</span> <span class="mi">3</span>
<span class="k">WHERE</span> <span class="n">status</span> <span class="o">=</span> <span class="ss">"A"</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">update</span><span class="p">(</span>
</span><span class="hll">   <span class="p">{</span> <span class="nx">status</span><span class="o">:</span> <span class="s2">"A"</span> <span class="p">}</span> <span class="p">,</span>
</span><span class="hll">   <span class="p">{</span> <span class="nx">$inc</span><span class="o">:</span> <span class="p">{</span> <span class="nx">age</span><span class="o">:</span> <span class="mi">3</span> <span class="p">}</span> <span class="p">},</span>
</span><span class="hll">   <span class="p">{</span> <span class="nx">multi</span><span class="o">:</span> <span class="kc">true</span> <span class="p">}</span>
</span><span class="hll"><span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.update/#db.collection.update" title="db.collection.update"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">update()</span></tt></a>,
<a class="reference internal" href="../operators/#_S_inc" title="$inc"><tt class="xref mongodb mongodb-operator docutils literal"><span class="pre">$inc</span></tt></a>, and <a class="reference internal" href="../operators/#_S_set" title="$set"><tt class="xref mongodb mongodb-operator docutils literal"><span class="pre">$set</span></tt></a> for more
information.</td>
</tr>
</tbody>
</table>
</div>
<div class="section" id="delete-records">
<h3>Delete Records<a class="headerlink" href="#delete-records" title="Permalink to this headline">¶</a></h3>
<p>The following table presents the various SQL statements related to
deleting records from tables and the corresponding MongoDB statements.</p>
<table border="1" class="docutils">
<colgroup>
<col width="21%">
<col width="35%">
<col width="44%">
</colgroup>
<thead valign="bottom">
<tr class="row-odd"><th class="head">SQL Delete Statements</th>
<th class="head">MongoDB remove() Statements</th>
<th class="head">Reference</th>
</tr>
</thead>
<tbody valign="top">
<tr class="row-even"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">DELETE</span> <span class="k">FROM</span> <span class="n">users</span>
<span class="k">WHERE</span> <span class="n">status</span> <span class="o">=</span> <span class="ss">"D"</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">remove</span><span class="p">(</span> <span class="p">{</span> <span class="nx">status</span><span class="o">:</span> <span class="s2">"D"</span> <span class="p">}</span> <span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.remove/#db.collection.remove" title="db.collection.remove"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">remove()</span></tt></a>
for more information.</td>
</tr>
<tr class="row-odd"><td><div class="first last highlight-sql"><div class="highlight"><pre><span class="k">DELETE</span> <span class="k">FROM</span> <span class="n">users</span>
</pre></div>
</div>
</td>
<td><div class="first last highlight-javascript"><div class="highlight"><pre><span class="hll"><span class="nx">db</span><span class="p">.</span><span class="nx">users</span><span class="p">.</span><span class="nx">remove</span><span class="p">(</span> <span class="p">)</span>
</span></pre></div>
</div>
</td>
<td>See <a class="reference internal" href="../method/db.collection.remove/#db.collection.remove" title="db.collection.remove"><tt class="xref mongodb mongodb-method docutils literal"><span class="pre">remove()</span></tt></a>
for more information.</td>
</tr>
</tbody>
</table>
</div>
</div>
</div>

## Mongoose Installation

- `$ sudo npm install mongoose`: install the latest Mongoose locally`
- `$ sudo npm install mongoose@3.8.20 --save`: install Mongoose v3.8.20 locally and save to `package.json`

## Mongoose Basic Usage

```
var mongoose = require('mongoose')
var dbUri = 'mongodb://localhost:27017/api'
var dbConnection = mongoose.createConnection(dbUri)
var Schema = mongoose.Schema
var postSchema = new Schema ({
  title: String,
  text: String
})
var Post = dbConnection.model('Post', postSchema, 'posts')
Post.find({},function(error, posts){
  console.log(posts)
  process.exit(1)
})
```

## Mongoose Schema

- `String`
- `Boolean`
- `Number`
- `Date`
- `Array`
- `Buffer`
- `Schema.Types.Mixed`
- `Schema.Types.ObjectId`

## Create, Read, Update, Delete (CRUD) Mongoose Example

```
// Create
var post = new Post({title: 'a', text: 'b')
post.save(function(error, document){
  ...
})


// Read
Post.findOne(criteria, function(error, post) {
  ...
})

// Update
Post.findOne(criteria, function(error, post) {
  post.set()
  post.save(function(error, document){
    ...
  })
})

// Delete
Post.findOne(criteria, function(error, post) {
  post.remove(function(error){
    ...
  })
})
```

## Mongoose Model Methods

- `find(criteria, [fields], [options], [callback])`: find document; callback has error and documents arguments
- `count(criteria, [callback]))`: return a count; callback has error and count arguments
- `findById(id, [fields], [options], [callback])`: return a single document by ID; callback has error and document arguments
- `findByIdAndUpdate(id, [update], [options], [callback])`: executes MongoDB's findAndModify to update by ID
- `findByIdAndRemove(id, [options], [callback])`: executes MongoDB's findAndModify to remove
- `findOne(criteria, [fields], [options], [callback])`: return a single document; callback has error and document arguments
- `findOneAndUpdate([criteria], [update], [options], [callback])`: executes MongoDB's findAndModify to update
- `findOneAndRemove(id, [update], [options], [callback])`: executes MongoDB's findAndModify to remove
- `update(criteria, update, [options], [callback])`: update documents; callbach has error, and count arguments
- `create(doc(s), [callback])`: create document object and save it to database; callback has error and doc(s) arguments
- `remove(criteria, [callback])`: remove documents; callback has error argument

## Mongoose Document Methods

- `save([callback])`: save the document; callback has error, doc and count arguments
- `set(path, val, [type], [options])`: set value on the doc's property
- `get(path, [type])`: get the value
- `isModified([path])`: check if the property has been modified
- `populate([path], [callback])`: populate reference
- `toJSON(options)`: get JSON from document
- `validate(callback)`: validate the document
