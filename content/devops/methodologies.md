+++
description = "Git, Scrum, CI/CD"
title = "Methodologies"
draft = false
weight = 100
bref="Methodologies to shorten the systems development life cycle while delivering features, fixes, and updates frequently in close alignment with business objectives"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">Version control</a></h3>
  <div class="example">
    <dl>
      <dt>Git</dt>
      <dd>A version-control system for tracking changes in computer files and coordinating work on those files among multiple people. It is used for source-code management in software development. As a distributed revision-control system, it is aimed at speed, data integrity, and support for distributed, non-linear workflows. Every Git directory on every computer is a full-fledged repository with complete history and full version-tracking abilities, independent of network access or a central server.</dd><br/>
      <dd><i>Below are the CLI commands for Git repositories.</i></dd>
    </dl>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.org/img/devops/git.png">
    </div><br/>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section2"><a href="#h-Section2">Agile software development</a></h3>
  <div class="example">
    <dl>
      <dt>Agile software development</dt>
      <dd>An approach to software development under which requirements and solutions evolve through the collaborative effort of self-organizing and cross-functional teams and their customer(s)/end user(s). It advocates adaptive planning, evolutionary development, early delivery, and continual improvement, and it encourages rapid and flexible response to change. One of the differences between agile software development methods and waterfall is the approach to quality and testing. In the waterfall model, there is always a separate testing phase after a build phase; however, in agile software development testing is completed in the same iteration as programming. </dd>
    </dl>
    <dl>
      <dt>Scrum</dt>
      <dd>An agile framework for managing knowledge work, with an emphasis on software development. It is designed for teams of three to nine members, who break their work into actions that can be completed within timeboxed iterations, called "sprints", no longer than one month and most commonly two weeks, then track progress and re-plan in 15-minute stand-up meetings, called daily scrums. </dd><br/>
      <dd><b>The Scrum process</b><br/>
<ol>
<li>Product owner creates a product backlog representing client needs (user stories)</li>
<li>Product backlog is broken up into one or more release backlogs</li>
<ul>
<li>Team estimates time and priority for all tasks</li>
<li>Team consists of product owner, scrum master (project manager), developers, and executives</li>
</ul>
<li>Release backlog converted into several sprint backlogs</li>
<ul>
<li>Each sprint (between 3 - 30 days) should result in a product release</li>
<li>Burnout chart determines progress of sprint</li>
<ul>
<li>Time estimation from previous step updated as team completes tasks</li>
</ul>
<li>Daily scrum - What have you done? What will you do? Any obstacles?</li>
</ul>
<li>Sprint review - Release product or repeat sprint; determine ways to improve sprint process</li>
</ol>
</dd>
    </dl>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.org/img/devops/agile.jpg">
    </div><br/>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section3"><a href="#h-Section3">CI/CD</a></h3>
  <div class="example">
    <p>CICD refers to the combined practices of continuous integration and continuous delivery. Continuous integration (CI) is the practice of merging all developer working copies to a shared mainline several times a day. Continuous delivery (CD) is a software engineering approach in which teams produce software in short cycles, ensuring that the software can be reliably released at any time. It aims at building, testing, and releasing software with greater speed and frequency. The approach helps reduce the cost, time, and risk of delivering changes by allowing for more incremental updates to applications in production.</p>
    <dl>
      <dt>The process in AWS</dt>
      <dd>
<ol>
<li>Setup AWS CodePipeline to trigger on changes to a source control like Git or AWS CodeCommit.</li>
<li>Use a <mark>Buildspec.yml</mark> containing build commands that AWS Codebuild can use to automatically create a build environment and run your build. </li>
<li>Any build output will be put into an Amazon S3 bucket. AWS CodePipeline will trigger AWS CodeDeploy to deploy these artifacts to an EC2 instance. </li>
<li>AWS CodePipeline will trigger automated integration & acceptance testing in this EC2 instance. This is the staging environment.</li>
<li>After tests have been run, AWS CodePipeline should wait for a manual checkpoint. After reviewing test reports, the decision maker can approve AWS CodeDeploy to deploy to production.</li>
</ol>
      </dd>
    <div style="text-align:center">
      <img alt="Image" src="https://www.javascripter.org/img/devops/CI_in_AWS.PNG">
    </div><br/>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section4"><a href="#h-Section4">AWS Well-Architected</a></h3>
  <div class="example">
    <p><a href="https://aws.amazon.com/architecture/well-architected/">AWS whitepaper</a> on the key concepts and design principles for architecting in the cloud. The 5 pillars are:</p>
    <dl>
      <dt>Operational Excellence</dt>
      <dd>The operational excellence pillar focuses on running and monitoring systems to deliver business value, and continually improving processes and procedures. Key topics include managing and automating changes, responding to events, and defining standards to successfully manage daily operations.</dd>
    </dl>
    <dl>
      <dt>Security</dt>
      <dd>The security pillar focuses on protecting information & systems. Key topics include confidentiality and integrity of data, identifying and managing who can do what with privilege management, protecting systems, and establishing controls to detect security events.</dd>
    </dl>
    <dl>
      <dt>Reliability</dt>
      <dd>The reliability pillar focuses on the ability to prevent, and quickly recover from failures to meet business and customer demand. Key topics include foundational elements around setup, cross project requirements, recovery planning, and how we handle change. </dd>
    </dl>
    <dl>
      <dt>Performance Efficiency</dt>
      <dd>The performance efficiency pillar focuses on using IT and computing resources efficiently. Key topics include selecting the right resource types and sizes based on workload requirements, monitoring performance, and making informed decisions to maintain efficiency as business needs evolve. </dd>
    </dl>
    <dl>
      <dt>Cost Optimization</dt>
      <dd>Cost Optimization focuses on avoiding un-needed costs. Key topics include understanding and controlling where money is being spent, selecting the most appropriate and right number of resource types, analyzing spend over time, and scaling to meet business needs without overspending. </dd>
    </dl>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

