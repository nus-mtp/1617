---
layout: page
title: On Wrapping Up
---

# Lecture 7: Wrapping Up

In this lecture, I will describe what are the key activities during Week 10 - 13
and the deliverables by Week 13.

During Week 10 - 13, you can continue to code, but it is expected you have
completed most of the high-value, low-risk features in the project.  You should
also spend time with evaluation and preparing for the final deliverables.

## Evaluation

You should evaluate and improve your application along four dimentions:

### Robustness

To evaluate how robust is your project, you should test it extensively, and fix
any bugs you find.  In addition, you should perform stress test to see how your
application behave under high load.  There could be unforseen issues (e.g.,
memory leaks, hitting the limits on the number of opened files) that only
manifest itself when there are many concurrent users.  

There are many existing tools for load testing.  You can use any tool that you
like.  Here are two that I use:

* [Apache Benchmark](https://httpd.apache.org/docs/2.4/programs/ab.html) (```ab```) is a web server benchmarking tool that allows
developers to generate multiple requests to the server. This is a very useful
tool to stress test the system, as well as to help with profiling the server.

* [Apache JMeter](http://jmeter.apache.org) is a general purpose load testing
and performance measurement tools, not limited to Web application.  As such, it
has a steeper learning curve but is much more powerful.

### Efficiency

We have talked about measuring performance, identifying bottleneck, and optimizing performance during [Lecture
6](n6-performance.html).  One thing I would like to add is that, some
performance issues only appear when the data size is big enough.  So, it is
important that you test with a database with realistic data size for your
application.

### Usability

We have also talked about usability issues and how to evaluate usability during
[Lecture 5](n5-usability.html).  I have gone through the heuristic evaluation
exercise with some teams, and will continue to do so.   

All teams should invoke the other two methods for usability evaluation sometime
during Week 10-13.  For System Usability Scale (SUS), use at least 15 real users
to evaluate.  For Think-Aloud Protocol, get 2-3 users.  

### Security

You should use an existing tool to automatically evaluate the security of your
application.  Many tools exist.  But one popular tool with many tutorials online
is [Zed Attack Proxy
(ZAP)](https://www.owasp.org/index.php/OWASP_Zed_Attack_Proxy_Project) from Open Web Application Security Project (OWASP).

ZAP is security tool that attacks your Web application to find common security vulnerability.  __DO NOT USE ZAP ON
ANY WEBSITE OTHER THAN YOUR OWN !!__  ZAP runs as a proxy between your browser
(some browser configuration needed) and your server.  

## Deliverables

### Code

The final push to ```master``` deployed to heroku will be read and executed for
grading purposes.

### Report

You need to submit a final report, written as Wiki on your Github repo.  It
should contain the following:

* Final software requirements, software design, and software architecture.
Please pay attention to how you implemented your software -- it should be
consistent with the design and architecture!

* Please include also details about how you elicited the software requirements
(interview/survey questions and results, comparisons with existing tools, etc).

* Document all your evaluation procedures and results for efficiency, usability,
security, and robustness above.

### Demonstration (Live and Video)

You need to demonstrate your project in class during lecture in Week 12 and
prepare a 2-minute demonstration video (uploaded to YouTube) for STePS and for your project website.

For demonstration, please populate your application with realistically looking
data (instead of "John Appleseed" instead of "test user" etc).  You can see any
of the Apple demonstration video during their keynotes or special events for
examples.  

A common mistake I have seen is a demo the runs through the features of the
project one-by-one.  A good demonstration should tell a story and show how 
the app would solve the users' problems and meet the users' needs.

BTW, here is an [amazing 5-minute
demo](https://www.youtube.com/watch?v=-VuXIgp9S7o) of Twilio.

### Website

Create a Github Project Page (you can use one of their templates) that includes
the goals and features of the project, the instructions to download, install,
and run, the instructions to contribute to the project, a link to the demo video
above (on YouTube), and information about each team members.

### Github Repo

Before CA3 deadline, you should configure your Github repo and checks in common
files that are informative about your project.  The repo name should be changed
if needed.  There should be a description about your project.

You should also have the following files:

* README.md -- overall information about the project
* LICENSE -- the software licence (pick a standard OSS license, my preference would be
MIT license)
* INSTALL.md -- instructions to install and run
* CONTRIBUTING.md -- how to contribute
* CHANGELOG.md -- major changes for different releases

To avoid overlaps, the website and the repo can cross-link each other.

### Poster

As part of STePS, you need to produce a poster as well.  In addition to the
required information (project ID, sponsors, etc) from STePS, your poster should
include the goals of the project, the key features and what problems they are
solving, screenshots, the softwre stack, and information about team members.

# CA3 Deadline

CA3 deadline is on Friday the 13th Week (14 April, 2359).
