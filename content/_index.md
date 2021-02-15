---
title: "GServlet API"
---

# GServlet API

[![Build Status @ Travis](https://api.travis-ci.com/GServlet/gservlet-api.png?branch=master)](https://travis-ci.com/GServlet/gservlet-api)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=GServlet_gservlet-api&metric=alert_status)](https://sonarcloud.io/dashboard?id=GServlet_gservlet-api)
[![Bugs](https://sonarcloud.io/api/project_badges/measure?project=GServlet_gservlet-api&metric=bugs)](https://sonarcloud.io/dashboard?id=GServlet_gservlet-api)
[![Vulnerabilities](https://sonarcloud.io/api/project_badges/measure?project=GServlet_gservlet-api&metric=vulnerabilities)](https://sonarcloud.io/dashboard?id=GServlet_gservlet-api)
[![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=GServlet_gservlet-api&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=GServlet_gservlet-api)
[![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=GServlet_gservlet-api&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=GServlet_gservlet-api)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=GServlet_gservlet-api&metric=security_rating)](https://sonarcloud.io/dashboard?id=GServlet_gservlet-api)
[![Coverage Status](https://coveralls.io/repos/github/GServlet/gservlet-api/badge.png?branch=master)](https://coveralls.io/github/GServlet/gservlet-api?branch=master)
[![follow on Twitter](https://img.shields.io/twitter/follow/gservlet?style=social)](https://twitter.com/intent/follow?screen_name=gservlet)

## Table of Contents

1. [Introduction](#introduction)
*  [Getting Started](#getting-started)
*  [Documentation](#documentation)
*  [Download](#download)
*  [Support](#support)
*  [Contribute](#contribute)

## Introduction

[GServlet](https://github.com/GServlet/gservlet-api) is an open source project inspired from the [Groovlets](http://docs.groovy-lang.org/latest/html/documentation/servlet-userguide.html), which aims to use the Groovy language and its provided modules to simplify Servlet API web development.
Groovlets are Groovy scripts executed by a servlet. They are run on request, having the whole web context (request, response, etc.) bound to the evaluation context. They are much more suitable for smaller web applications. Compared to Java Servlets, coding in Groovy can be much simpler. It has a couple of implicit variables we can use, for example, _request_, _response_ to access the **HttpServletRequest**, and **HttpServletResponse** objects. We have access to the **HttpSession** with the _session_ variable. If we want to output data, we can use _out_, _sout_, and _html_. This is more like a script as it does not have a class wrapper.

#### Groovlet

```java
if (!session) {
    session = request.getSession(true)
}
if (!session.counter) {
    session.counter = 1
}
html.html {
  head {
      title('Groovy Servlet')
  }
  body {
    p("Hello, ${request.remoteHost}: ${session.counter}! ${new Date()}")
  }
}
session.counter = session.counter + 1
```

The same philosophy has been followed in the design of this API while maintaining a class-based programming approach.

#### SessionCounterServlet.groovy
 
```java
import org.gservlet.annotation.Servlet

@Servlet("/counter")
class SessionCounterServlet {

  void get() {
    if (!session.counter) {
      session.counter = 1
    }
    html.html {
      head {
        title('Groovy Servlet')
      }
      body {
        p("Hello, ${request.remoteHost}: ${session.counter}! ${new Date()}")
      }
    }
    session.counter = session.counter + 1
  }

}
```

## Getting Started

Get ready to get started and running in less than 5 minutes. We provide in our [getting started](/learn) page a step-by-step guide. 

## Documentation

In our [documentation](/documentation) page, you'll find all the documentation for in-depth knowledge of this project. The Javadocs for a particular version can be found as well.  

## Download

If you want to download the artifact without a dependency management tool or want to build it from the source, we cover how to achieve it in our [download](/download) page. The current version of GServlet is [1.0.1 (https://mvnrepository.com/artifact/org.gservlet/gservlet-api/1.0.0). You can search for previous releases on [Maven Central](https://mvnrepository.com/artifact/org.gservlet/gservlet-api).

## Support

There are numerous ways to get help with GServlet. Find out how in our [support](/support) page.

## Contribute

Would you like to contribute to the project? There are many ways in which you can bring your participation. We provide more information about how to get involved in our [contribute](/contribute) page. GServlet is an Open Source software released under the [Apache 2.0 license](http://www.apache.org/licenses/LICENSE-2.0.html) and it can be found on [GitHub](https://github.com/GServlet/gservlet-api).