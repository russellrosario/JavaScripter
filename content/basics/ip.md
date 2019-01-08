+++
description = "Networks, HTTP, TCP/IP, DNS"
title = "Internet protocols"
draft = false
weight = 300
bref="Rules and guidelines established to promote consistency in the design code which makes up a web page"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">Networks</a></h3>
  <div class="example">
    <dl>
      <dt>LAN</dt>
      <dd>A computer network that spans a relatively small area connected via ethernet and wifi.</dd>
    </dl>
    <dl>
      <dt>WAN</dt>
      <dd>A computer network that spans a large area by connecting multiple LANs. The largest WAN in existence is the Internet.</dd>
    </dl>
    <dl>
      <dt>VPN</dt>
      <dd>Extends a private network across a public network, and enables users to send and receive data across shared or public networks as if their computing devices were directly connected to the private network.</dd>
    </dl>
    <dl>
      <dt>IP address</dt>
      <dd>A numerical label assigned to each device connected to a computer network that uses the Internet Protocol for communication. When communicating with devices within the network, a private IP address is used. When communicating with devices outside the network, a public IP address is used. Since all devices within a private network share the same public IP address, port forwarding and network address translation is used by the router to determine how to route data among devices. <a href="https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing">CIDR</a> is a method for dividing networks into subnetworks.</dd>
    </dl>
    <div style="text-align:center">
      <figure>
        <img alt="Image" src="https://www.javascripter.co/img/basics/AWS_VPC.png">
        <figcaption>
          An example of a cloud VPN on AWS
        </figcaption>
      </figure>
    </div>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section2"><a href="#h-Section2">TCP/IP</a></h3>
  <div class="example">
  <p>The Internet protocol suite (TCP/IP) provides end-to-end data communication specifying how data should be packetized, addressed, transmitted, routed, and received. This functionality is organized into abstraction layers.</p>
  <dl>
      <dt>Link/physical</dt>
      <dd>The link layer is used to move packets between the Internet layer interfaces of two different hosts on the same link using MAC addresses. This is also the layer where packets may be selected to be sent over a VPN. In this scenario, the link layer data may be considered application data allowing it to traverse over the layers again before being transmitted.</dd>
    </dl>
    <dl>
      <dt>Internet</dt>
      <dd>The primary protocol in this scope is the Internet Protocol, which defines IP addresses. Its function in routing is to transport datagrams to the next IP router that has the connectivity to a network closer to the final data destination.</dd>
    </dl>
    <dl>
      <dt>Transport</dt>
      <dd>Handling host-to-host communication. TCP provides reliable, ordered, and error-checked delivery of a stream of octets (bytes) between applications running on hosts communicating via an IP network. Applications that do not require reliable data stream service may use the User Datagram Protocol (UDP), which provides a connectionless datagram service that emphasizes reduced latency over reliability.</dd>
    </dl>
    <dl>
      <dt>Application</dt>
      <dd>Providing process-to-process data exchange for applications. This is the layer in which all higher level protocols, such as SMTP, FTP, SSH, HTTP, operate. Processes are addressed via ports which essentially represent services.</dd>
    </dl>
    <p> </p>
    <div class="row">
      <div class="col col-6">
      <figure>
        <img alt="Image" src="/img/basics/tcp2.png">
      </figure>
      </div>
      <div class="col col-6">
        <figure style="margin-top:50px">
          <img alt="Image" src="/img/basics/tcp.jpg">
        </figure>
      </div>
    </div>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section3"><a href="#h-Section3">HTTP</a></h3>
  <div class="example">
  <p>The client and server communicate by sending plain-text (ASCII) messages. The client sends requests to the server and the server sends responses. </p>
  <p>The request message consists of the following:</p>
  <ul>
    <li>a request line with an HTTP method, URI, and HTTP version (e.g., GET /images/logo.png HTTP/1.1, which requests a resource called /images/logo.png from the server.)</li>
    <li>request header fields (e.g., Accept-Language: en).</li>
    <li>an empty line</li>
    <li>an optional message body</li>
  </ul>
<pre><code>GET /guide/index.html HTTP/1.1
Host: www.xxxx.com
Accept: image/gif, image/jpeg, */*
Accept-Language: en-us
Accept-Encoding: gzip, deflate
User-Agent: Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)
(blank line)
</code></pre>

  <p>The response message consists of the following:</p>
  <ul>
    <li>a status line with a status code with message and HTTP version (e.g., HTTP/1.1 200 OK, which indicates that the client's request succeeded.)</li>
    <li>response header fields (e.g., Content-Type: text/html)</li>
    <li>an empty line</li>
    <li>an optional message body</li>
  </ul>
<pre><code>HTTP/1.1 200 OK
Date: Sun, 18 Oct 2015 08:56:53 GMT
Server: Apache/2.2.14 (Win32)
Last-Modified: Sat, 20 Nov 2015 07:16:26 GMT
ETag: "10000000565a5-2c-3e94b66c2e680"
Accept-Ranges: bytes
Content-Length: 44
Connection: close
Content-Type: text/html
X-Pad: avoid browser bug<br/>
&lt;html&gt;&lt;body&gt;&lt;h1&gt;Guide&lt;/h1&gt;&lt;p&gt;This is guide on HTTP protocol&lt;/p&gt;&lt;/body&gt;&lt;/html&gt;</code></pre>

</div>

<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section4"><a href="#h-Section4">DNS</a></h3>
  <div class="example">
  <p>The Domain Name System (DNS) is a worldwide, distributed database for translating easily memorized domain names into IP addresses needed for communication over the internet. Each domain has at least one authoritative DNS server that stores records such as IP addresses (A and AAAA), SMTP mail exchangers (MX), name servers (NS), and domain name aliases (CNAME). Name servers "point" your domain name to the company that controls its DNS settings.</p>

  <p>DNS resolution occurs by first looking up the name server for the TLD (.com or .net), then the name server for the full domain (medium.com), and lastly the numeric IP of the subdomain with domain (www.medium.com). To reduce the load on the Domain Name System servers, results are cached locally or in intermediate resolver hosts. A time to live (TTL) is included with the cached results, an expiration time after which the results must be discarded or refreshed.</p>
    <div style="text-align:center">
      <img src="https://www.javascripter.co/img/basics/dns.png">
    </div>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

