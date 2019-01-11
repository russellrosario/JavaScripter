+++
description = "Containers, Serverless, performance"
title = "Scalability"
draft = false
weight = 500
bref="Scalability is the capability of a system, network, or process to handle a growing amount of work, or its potential to be enlarged to accommodate that growth"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">Containers</a></h3>
  <div class="example">
  <p>An operating system feature in which the kernel allows the existence of multiple isolated user-space instances called containers. Containers isolate software from its environment so that it may run uniformly on all machines.</p>
    <div class="row">
      <div class="col col-6" style="text-align:center">
        <figure>
          <img alt="Image" src="https://www.javascripter.co/img/devops/container1.PNG" width="85%">
          <figcaption>
          Container
          </figcaption>
        </figure>
      </div>
      <div class="col col-6" style="text-align:center">
        <figure>
          <img alt="Image" src="https://www.javascripter.co/img/devops/container2.PNG" width="85%">
          <figcaption>
            Virtual machine
          </figcaption>
        </figure>
      </div>
    </div>
    <dl>
      <dt>Containerization</dt>
      <dd>A container is a runtime instance of an image--what the image becomes in memory when executed (an image with state). An <b>image</b> is an executable package that includes everything needed to run an application--the code, a runtime, libraries, environment variables, and configuration files. Containers are a key enabling technology for microservices, providing a lightweight encapsulation of each component so that it is easy to maintain and replicate. </dd>
      <dt>Microservices</dt>
      <dd>An architectural style that structures an application as a collection of loosely coupled services. The benefit of decomposing an application into different smaller services is that it improves modularity. This makes the application easier to understand, develop, test, and become more resilient to architecture erosion. It parallelizes development by enabling small autonomous teams to develop, deploy and scale their respective services independently. It also allows the architecture of an individual service to emerge through continuous refactoring. </dd>
    </dl>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/devops/microservices.png">
    </div>
    <dl>
      <dt>Docker</dt>
      <dd>A platform for developers and sysadmins to develop, deploy, and run applications with containers. </dd><br/>
      <dd>The Docker <b>Client</b> runs commands like <mark>docker build</mark> or <mark>docker run</mark>. The Docker <b>Daemon</b> (aka Host or Engine) makes the system calls to create, operate and manage containers. Many of the configurations in Docker image will from Docker <b>Registry</b> where it will be downloaded. </dd>
      <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/devops/docker.png" width ="85%">
    </div><br/>
      <dd><b>Swarm</b> is a native clustering tool for Docker. Swarm pools together several Docker hosts and exposes them as a single virtual Docker host. In Swarm mode, there are two types of nodes: Managers and workers. Manager nodes maintain cluster state and schedule services. Worker nodes execute containers. Clustering is an important feature for container technology, because it creates a cooperative group of systems that can provide redundancy through failover and scalability through automation.</dd>
    </dl>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/devops/swarm.png">
    </div><br/>
    <dd><b>AWS ECS</b> and <b>Kubernetes</b> are two alternate services for maintaining and coordinating clusters of container. <i>Their functionlity is similar</i>.</dd>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section2"><a href="#h-Section2">Serverless</a></h3>
  <div class="example">
    <dl>
      <dt>Benefits</dt>
      <dd><ul>
      <li><b>Pay per use</b> - paying for use rather than capacity can be significantly cheaper depending on use case</li>
      <li><b>Scalability</b> - horizontal scaling is built into the platform</li>
      <li><b>Faster development</b> - functions can be built standalone, independent from the rest of the application.</li>
      <li><b>Maintenance</b> - vendor handles server upgrades and maintenance.</li>
      </ul>
      </dd>
      <dt>Drawbacks</dt>
      <dd>      <ul>
      <li><b>3rd party API</b> - vendor lock-in</li>
      <li><b>Lack of operational tools</b> - debugging and testing are difficult</li>
      <li><b>Architectural complexity</b> - as functions get more granular, the wiring between those functions increases exponentially.</li>
      <li><b>Timeouts & Latency</b> - becuase serverless functions run in ephemeral containers, there is increased latency when the container does not yet exist. In addition, there is a timeout which prevents long running functions from executing to completion.</li>
      </ul> </dd>
    </dl>
    <dl>
      <dt>Serverless framework</dt>
      <dd>Infrastructure as code </dd>
      <dd>Alternatives - Vendor agnostic, language independent, packages functions, larger community (plugins)</dd>
    </dl>
     <dl>
      <dt>serverless.yml</dt>
      <dd>Services</dd>
      <dd>Functions & events</dd>
      <dd>Layers</dd>
      <dd>Resources</dd>
      <dd>Variables</dd>
      <dd>export, import, cloudformation, join ref </dd>
      <dd>Deploying</dd>
      <dd>https://serverless.com/framework/docs/providers/aws/guide/serverless.yml/</dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section3"><a href="#h-Section3">Web performance</a></h3>
  <div class="example">
    <dl>
      <dt>Load balancing and Autoscaling</dt>
      <dd>A load balancer is a device that acts as a reverse proxy and distributes network or application traffic across a number of servers. Autoscaling is when computational resources in a server farm, typically measured in terms of the number of active servers, scales automatically based on the load on the farm. When using containers, orchestration services <ins>Kubernetes and Amazon ECS handle load balancing and autoscaling</ins> for you.</dd><br/>
      <dt>CDN</dt>
      <dd>A content delivery network (CDN) refers to a geographically distributed group of servers which work together to provide fast delivery of Internet content. A CDN allows for the quick transfer of static assets needed for loading Internet content including HTML pages, javascript files, stylesheets, images, and videos. Using a CDN improves website load times, reduces bandwidth costs, increases content availability and redundancy, and improves website security (e.g. DDoS mitigation).</dd><br/>
      <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/devops/cdn.png">
    </div>
      <dt>Caching</dt>
      <dd>A <b>cache</b> A hardware or software component that stores data so that future requests for that data can be served faster; the data stored in a cache might be the result of an earlier computation or a copy of data stored elsewhere. A CDN is an example of a cache when a user retrieves assets from an edge location rather than a distant origin server. Web browsers also uses caches that store static data rather than re-retrieve them. The timeframe for how long these items stay cached can be set by a <b>cache header</b> or <b>service worker</b>. For databases, <b>Redis</b> can be used to intercept requests and send cached data rather than querying the database additional times for the same data.</dd><br/>
      <dt>Data transfer</dt>
      <dd><b>QUIC</b> - An experimental transport layer network protocol that is built on top of UDP. It handles error handling without the handshaking that the higher latency protocol TCP has.</dd>
      <dd><b>Compression</b> - compress all static assets. Also make sure your server uses <b>gzip</b> - a file format and a software application used for file compression and decompression.<br/></dd>
      <dd><b>Lazy loading</b> - Transfer data to the client as it is needed like a stream, rather than having them wait for the entire bundle to complete downloading.
      </dd><br/>
      <dt>Language selection</dt>
      <dd><b>Java</b> - For some tasks a different language might be necessary for performance gains. Java is an excellent language for computationally intensive operations. IO operations, on the other hand, might be better served using Node.js.</dd>
      <dd><b>WebAssembly</b> - a web standard that defines a binary format and a corresponding assembly-like text format for executable code in Web pages. It is meant to enable executing code nearly as quickly as running native machine code. Many believe WebAssembly could replace JavaScript entirely in the distant future.</dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

