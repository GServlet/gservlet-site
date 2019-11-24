---
title: "Getting Started"
chapter : true
weight: 1
pre : "<b>1. </b>"
---

# Getting Started

To get started with GServlet, you may want to begin by creating your first project. This section shows you how to get up and running quickly. It is highly recommended to consume the GServlet API through a dependency management tool and the artifact can be found in Maven's central repository. it is named _gservlet-api_ and you just need to name a dependency on it in your project.

## Installation

### From Maven

#### pom.xml

```xml

<dependency>
	<groupId>org.gservlet</groupId>
	<artifactId>gservlet-api</artifactId>
	<version>1.0.0</version>
</dependency>

```

### From Gradle

#### build.gradle

```java

dependencies {
    implementation 'org.gservlet:gservlet-api:1.0.0'
}

```

### Building from source

    > git clone git@github.com:gservlet/gservlet-api.git
    > cd gservlet-api
    > mvn clean install