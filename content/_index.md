---
title: "GServlet API"
---

# Welcome To GServlet

## The Vision

GServlet is an open source project inspired from the [Groovlets](http://docs.groovy-lang.org/latest/html/documentation/servlet-userguide.html), which aims to use the Groovy language and its provided modules to simplify Servlet API web development.
Groovlets are Groovy scripts executed by a servlet. They are run on request, having the whole web context (request, response, etc.) bound to the evaluation context. They are much more suitable for smaller web applications. 
Compared to Java Servlets, coding in Groovy can be much simpler. It has a couple of implicit variables we can use, for example, request, response to access the [_HttpServletRequest_](https://javaee.github.io/javaee-spec/javadocs/javax/servlet/http/HttpServletRequest.html), and [_HttpServletResponse_](https://javaee.github.io/javaee-spec/javadocs/javax/servlet/http/HttpServletResponse.html) objects. We have access to the [_HttpSession_](https://javaee.github.io/javaee-spec/javadocs/javax/servlet/http/HttpSession.html) with the session variable. If we want to output data, we can use _out_, _sout_, and _html_. This is more like a script as it does not have a class wrapper.

### Groovlet

```java

if (!session) {
    session = request.getSession(true)
}
if (!session.counter) {
    session.counter = 1
}
html.html { // html is implicitly bound to new MarkupBuilder(out)
  head {
      title('Groovy Servlet')
  }
  body {
    p("Hello, ${request.remoteHost}: ${session.counter}! ${new Date()}")
  }
}
session.counter = session.counter + 1

```

## Features

* Groovy Scripting
* Live Development
* Hot Reloading
* JSON and XML Support
* RDMS Support

## Requirements

* Java 7+
* Java IDE (Eclipse, IntelliJ IDEA, NetBeans..)
* Java EE 8 compliant WebServer (Tomcat, Wildfly, Glassfish, Payara..)

## Getting Started

to know how to get started, click on this link. 

## Documentation

to read the documentation, click on this link.

## Download

to know how to download the artifacts, click on this link.

## Support

to get a support, click on this link.

## Contribute

to know how to contribute, click on this link.