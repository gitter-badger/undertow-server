---
date: 2016-10-09T08:15:27-04:00
title: spring is bloated
---
## Introduction

Over the years, Spring seemed to be the replacement of JEE servers with IoC
container and light weight servlet container as its foundation. Especially
recently, Spring Boot brings in an easy development model and increases 
developer productivity dramatically.

However, there are two issues or limitations in Spring applications. 

### Spring is bloated and it becoming too heavy

When Spring was out, it was only a small core with IoC contains and it was
fast and easy to use. Now, I cannot even count how many Spring Components
available. In order to complete with JEE, Spring basically implemented all
replacements of JEE and these are heavy components.


### Spring is based on old servlet API and it is slow.

Another issue with Spring is due to the foundation of servlet container
which was designed over ten years ago without multi-core, NIO etc in
consideration. There is a little improvement in Servlet 3.1 but it wasn't
right due to backward compatible requirement. 

I did a performance test between Spring Boot and My own Undertow Framework
and Spring Boot is 44 times slower and the code and test result can be
found [here](https://github.com/networknt/undertow-server-example/tree/master/performance)

The test result for Spring Boot was based on the embedded tomcat server and
later on I have switched to Undertow servlet container for Spring Boot. The
Undertow Servlet container is faster but still over 20 times slower then
Undertow Framework. 

The 20 times difference between the two is due to Servlet overhead and Sprint
Boot overhead and it is very significant.




