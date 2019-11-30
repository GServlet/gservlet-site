---
title: "GServlet API"
---

# GServlet

[![Build Status @ Travis](https://api.travis-ci.com/GServlet/gservlet-api.png?branch=master)](https://travis-ci.com/GServlet/gservlet-api)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=GServlet_gservlet-api&metric=alert_status)](https://sonarcloud.io/dashboard?id=GServlet_gservlet-api)
[![Bugs](https://sonarcloud.io/api/project_badges/measure?project=GServlet_gservlet-api&metric=bugs)](https://sonarcloud.io/dashboard?id=GServlet_gservlet-api)
[![Vulnerabilities](https://sonarcloud.io/api/project_badges/measure?project=GServlet_gservlet-api&metric=vulnerabilities)](https://sonarcloud.io/dashboard?id=GServlet_gservlet-api)
[![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=GServlet_gservlet-api&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=GServlet_gservlet-api)
[![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=GServlet_gservlet-api&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=GServlet_gservlet-api)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=GServlet_gservlet-api&metric=security_rating)](https://sonarcloud.io/dashboard?id=GServlet_gservlet-api)
[![Coverage Status](https://coveralls.io/repos/github/GServlet/gservlet-api/badge.png?branch=master)](https://coveralls.io/github/GServlet/gservlet-api?branch=master)
[![License](http://img.shields.io/:license-apache-blue.png)](http://www.apache.org/licenses/LICENSE-2.0.html)

## Introduction

GServlet is an open source project inspired from the [Groovlets](http://docs.groovy-lang.org/latest/html/documentation/servlet-userguide.html), which aims to use the Groovy language and its provided modules to simplify Servlet API web development.
Groovlets are Groovy scripts executed by a servlet. They are run on request, having the whole web context (request, response, etc.) bound to the evaluation context. They are much more suitable for smaller web applications. 
Compared to Java Servlets, coding in Groovy can be much simpler. It has a couple of implicit variables we can use, for example, _request_, _response_ to access the [_HttpServletRequest_](https://javaee.github.io/javaee-spec/javadocs/javax/servlet/http/HttpServletRequest.html), and [_HttpServletResponse_](https://javaee.github.io/javaee-spec/javadocs/javax/servlet/http/HttpServletResponse.html) objects. We have access to the [_HttpSession_](https://javaee.github.io/javaee-spec/javadocs/javax/servlet/http/HttpSession.html) with the _session_ variable. If we want to output data, we can use _out_, _sout_, and _html_. This is more like a script as it does not have a class wrapper.

#### Groovlet

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

## Main Features

* Groovy Scripting
* Live Development
* Hot Reloading
* JSON and XML Support
* RDMS Support

## Requirements

* Java 7+
* Java IDE (Eclipse, IntelliJ IDEA, NetBeans..)
* Java EE 6+ compliant WebServer (Tomcat, Wildfly, Glassfish, Payara..)

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