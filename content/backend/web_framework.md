+++
description = "REST, Express.js, Authentication, security, deployment"
title = "Web Framework"
draft = false
weight = 300
bref="A web framework is a software framework that is designed to support the development of web applications including web services, web resources, and web APIs"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section0"><a href="#h-Section0">REST</a></h3>
  <div class="example">
    <p>Representational State Transfer (REST) is a software architectural style that defines a set of constraints for creating web services over <a href="http://localhost:1313/basics/ip/#h-Section3">HTTP.</a></p>
    <dl>
      <dt>6 guiding constraints</dt>
      <dd><ul>
        <li><b>Client–server architecture</b> - a distributed application structure that partitions tasks or workloads between the providers of a resource or service, called servers, and service requesters, called clients.</li>
        <li><b>Statelessness</b> - Each request from any client contains all the information necessary to service the request, and session state is held in the client (not the server). </li>
        <li><b>Cacheability</b> - Responses must, implicitly or explicitly, define themselves as cacheable or not to prevent clients from getting stale or inappropriate data in response to further requests. </li>
        <li><b>Layered system</b> - A client cannot ordinarily tell whether it is connected directly to the end server, or to an intermediary along the way.</li>
        <li><b>Code on demand (optional)</b> - Servers can temporarily extend or customize the functionality of a client by transferring executable code such as JavaScript client side scripts.</li>
        <li><b>Uniform interface</b> - Constraints that decouple the client interface from the server implementation. These include how to identify resources, describe metadata, and represent data. See <a href="http://localhost:1313/basics/ip/#h-Section3">HTTP protocol</a> for a better understanding of the constraints needed.</li>
        </ul></dd>
      <dt>Other methods </dt>
      <dd><b>GraphQL</b> - an open-source data query and manipulation language for developing flexible APIs. It allows clients to define the structure of the data required, and exactly the same structure of the data is returned from the server, therefore preventing excessively large amounts of data from being returned, but this has implications for how effective web caching of query results can be. The flexibility and richness of the query language also adds complexity that may not be worthwhile for simple APIs.</dd>
      <dd><b>Websockets</b> - a computer communications protocol facilitating real-time data transfer between client and server. The protocol is located at the application layer of the TCP/IP model and depend on TCP at layer 4. The WebSocket handshake uses the HTTP Upgrade header to change from the HTTP protocol to the WebSocket protocol (also compatible with HTTP). This allows messages to be passed back and forth while keeping the connection open. The communications are done over TCP port number 80 (or 443 in the case of TLS-encrypted connections).</dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">Express.js</a></h3>
  <div class="example">
  <p>An open-source web application framework using Node.js designed for building web applications and APIs. </p>
    <dl>
      <dt>Routing</dt>
      <dd>Routing refers to determining how an application responds to a client request to a particular endpoint, which is a URI (or path) and a specific HTTP request method (GET, POST, and so on). Express is configured to handle routes and HTTP verb with <mark>app.METHOD(PATH, HANDLER)</mark>.</dd><br/>
      <dt>Static files</dt>
      <dd>To serve static files such as images, CSS files, and JavaScript files, use the <mark>express.static</mark> built-in middleware function. Express also supports templating. A <b>template engine</b> enables you to use static template files in your application. At runtime, the template engine replaces variables in a template file with actual values, and transforms the template into an HTML file sent to the client. Pug, Handlebars, Jade are different template engines you can choose, each with their own syntax. </dd><br/>
      <dt>Middleware</dt>
      <dd>Middleware functions are functions that have access to the request object (req), the response object (res), and the next middleware function in the application’s request-response cycle. </dd>
      <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/backend/middleware.PNG">
    </div>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section2"><a href="#h-Section2">Authentication</a></h3>
  <div class="example">
    <dl>
      <dt>Hashing and salting</dt>
      <dd>Hashing performs a one-way transformation on a password, turning the password into another string, called the hashed password. Salting is adding random data as an additional input to the hash function. Authentication then relies on comparing the salt + hash of the original password. This protects commonly used passwords or users who use the same password on several sites, by making all salted hash instances for the same password different from each other.</dd>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/backend/salt_hash.png">
      <figcaption>
      Preventing reverse engineering via brute forcing the hash algorithm
      </figcaption>
    </div><br/>
      <dt>Cookies vs tokens</dt>
      <dd>Cookie-based authentication is stateful. This means that an authentication record or session must be kept both server and client-side. Token-based authentication is stateless. The server does not keep a record of which users are logged in or which tokens have been issued. Instead, every request to the server is accompanied by a signed token which the server uses to verify the authenticity of the request. Today, most authentication has moved from cookie-based to token-based.</dd>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.co/img/backend/cookie_token.png">
    </div><br/>
      <dt>Authentication libraries</dt>
      <dd><b>Passport</b> -  authentication middleware for Node that provides "strategies" for handling all types of authentication mechanisms. <b>JWT</b> (JSON web tokens) and <b>OAuth</b> (login with Facebook/Google account) are the most common. </dd><br/>
      <dd><b>Third party</b> - Ideally, you don't want to be handling sensitive data that can be hacked. Allowing a 3rd party to handle validation is best practice. AWS Cognito and Auth0 are two of the more popular authentication providers.</dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section3"><a href="#h-Section3">Deployment</a></h3>
  <div class="example">
    <dl>
      <dt>Heroku</dt>
      <dd>The easiest way to deploy Express apps is through Heroku, a cloud platform as a service supporting Node.js and many other languages. A platform-based service is a category of cloud computing services that provides a platform allowing customers to develop, run, and manage applications without the complexity of building and maintaining the infrastructure typically associated with developing and launching an app.<dd><br/>
      <dd>Once the Heroku CLI is installed, deployment is a simple <mark>heroku create</mark> command and Heroku will handle dependencies, installation, runtime environment, and all other deployment tasks. The Heroku Platform uses the container model to run and scale all Heroku apps. </dd>
    </dl>
    <dl>
      <dt>AWS</dt>
      <dd>AWS provides a similar service to Heroku called Elastic Beanstalk. They also provide virtual machines called EC2 instances. Deploying an app in this manner is a little more cumbersome.</dd>
      <dd><ol>
        <li>Create EC2 instance</li>
        <li>Access EC2 instance through SSH (using PEM/PPK file)</li>
        <li>Download and Install node on the instance</li>
        <li>Clone repository (from version control like GitHub)</li>
        <li>Install app dependencies</li>
        <li>Run the app in the node runtime</li>
        <li>Expose ports on the instance for public access</li>
        </ol></dd><br/>
      <dd>Choose AWS when you need infrastructure flexibility and understand DevOps. It is also the cheaper option as the app grows in complexity and use. Choose Heroku for smaller projects or when you don't want to deal with DevOps. </dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section4"><a href="#h-Section4">Security</a></h3>
  <div class="example">
    <dl>
      <dt>Dependencies</dt>
      <dd>Don’t use deprecated or vulnerable versions of your dependencies. Use <mark>npm audit fix</mark> to scan your project for vulnerabilities and automatically install any compatible updates to vulnerable dependencies. Alternatively, use <a href="https://snyk.io/"> Snyk.io</a>.</dd><br/>
      <dt>SSL/TLS Certificate</dt>
      <dd>In HTTPS, the communication protocol is encrypted using Transport Layer Security (TLS) to encrypt data before it is sent from the client to the server, thus preventing some common hacks (Man in the middle). HTTPS is based on <b>public/private-key cryptography</b>. This means that there is a key pair: The public key is used for encryption and the secret private key is required for decryption. A website certificate is a public key with a label identifying the owner. when your browser connects to an HTTPS server, the server will answer with its certificate. The browser checks if the certificate is valid and signed by a trusted certification authority. After the verification, the browser extracts the public key and uses it to encrypt information it sends back to the server. The server can decrypt it because the server has the matching private key.
</dd><br/>
    <div style="text-align:center" width="85%">
      <img alt="Image" src="https://www.javascripter.co/img/backend/key_encryption.png">
    </div><br/>
      <dt>Set security related HTTP headers</dt>
      <dd><b>Cross-origin resource sharing (CORS)</b> is a mechanism that allows restricted resources on a web page to be requested from another domain outside the domain from which the first resource was served. A web page may freely embed cross-origin images, stylesheets, scripts, iframes, and videos. Certain "cross-domain" requests, notably Ajax requests, are forbidden by default by the same-origin security policy. These have to be set explicitly on the header.</dd><br/>
      <dd>There are many other security related headers. Use a middleware function like <a href="https://helmetjs.github.io/">Helmet</a> to set these for you.</dd><br/>
      <dt>Learn common vulnerabilities</dt>
      <dd><ul>
        <li><b>Cross-site scripting (XSS)</b> - enables attackers to inject client-side scripts into web pages viewed by other users. </li>
        <li><b>SQL injection</b> - nefarious SQL statements are inserted into an entry field for execution (e.g. to dump the database contents to the attacker)</li>
        <li><b>Cross-Site Request Forgery (CSRF)</b> - unauthorized commands are transmitted from a user that the web application trusts.</li>
        <li><b>Distributed Denial-of-service attack (DDoS)</b> - flooding the server or resource with superfluous requests in an attempt to overload systems and prevent some or all legitimate requests from being fulfilled.</li>
        </ul></dd><br/>
      <dt>Secure development environments as well</dt>
      <dd><ul>
        <li><b>Successful key management</b> - involves dealing with the generation, exchange, storage, use, destruction and replacement of keys. It is the more challenging side of cryptography as it involves aspects of social engineering, system policy, user training, organizational and departmental interactions, and coordination between all of these elements.</li>
        <li><b>Principle of least privilege</b> - Every process, user, or program must be able to access only the information and resources that are necessary for its legitimate purpose and nothing more. This especially applies in teams of developers.</li>
        <li><b>Use VPN</b> - encrypt data if using unsecured or untrustworthy networks vulnerable to packet sniffing and man-in-the-middle attacks.</li>
        <li><b>Monitor system</b> - Check open ports and unrecognized running processes</li>
        </ul></dd><br/>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>