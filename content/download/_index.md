---
title: "Download"
chapter : true
weight: 3
pre : "<b>3. </b>"
---

# Download

The recommended way of getting GServlet is to declare a dependency on the _gservlet-api_ library using your favorite build tools but you can build it also from the latest source code in the GitHub [repository](https://github.com/GServlet/gservlet-api).


## From your build tools

#### Maven

```xml
<dependency>
	<groupId>org.gservlet</groupId>
	<artifactId>gservlet-api</artifactId>
	<version>1.0.0</version>
</dependency>
```

#### Gradle

```
dependencies {
    implementation 'org.gservlet:gservlet-api:1.0.0'
}

```


## Building from source

    > git clone git@github.com:gservlet/gservlet-api.git
    > cd gservlet-api
    > mvn clean install


### Documentation

The documentation which is generated with Maven is based on [Asciidoctor](http://asciidoctor.org/). Only the HTML output is enabled.

    > mvn clean install -Pdocumentation

The built documentation can then be found in the following location:
  
    > ./target/generated-docs
    
On the other hand, the javadocs can be found in the folder:

    > ./target/site/apidocs    

We use [UMLGraph](https://www.spinellis.gr/umlgraph/index.html) to generate UML class diagrams which are embedded in the javadocs, therefore you must have [Graphviz](https://www.graphviz.org/) installed in your computer and the **GraphvizX.XX\bin** directory added to your system PATH.