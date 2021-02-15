---
title: "Download"
chapter : true
weight: 3
pre : "<b>3. </b>"
---

# Download

The recommended way of getting GServlet is to declare a dependency on the _gservlet-api_ library using your favorite build tools but you can build it also from the latest source code in the GitHub [repository](https://github.com/GServlet/gservlet-api). The current release is 1.0.1. You can search for previous releases on [Maven Central](https://mvnrepository.com/artifact/org.gservlet/gservlet-api).

## Releases

| Release     | Release Date    | Changelog                       |
| ----------- | --------------- | -------------------------------
| 1.0.1       | 4 January 2021  | [Changelog](/changelogs/1.0.1)  |
| 1.0.0       | 4 January 2021  | [Changelog](/changelogs/1.0.0)  |

## From your build tools

#### Maven

```xml
<dependency>
	<groupId>org.gservlet</groupId>
	<artifactId>gservlet-api</artifactId>
	<version>${gservlet.version}</version>
</dependency>
```

#### Gradle

```
repositories {
    mavenCentral()
}

dependencies {
    compile("org.gservlet:gservlet-api:${gservletVersion}")
}

```

## Release Plan

* 1.0.x : Java EE 7+ and Jakarta EE 8 support
* 2.0.x : Jakarta EE 9 support
* 3.0.x : Jakarta EE 10 support

## Snapshot builds

You can access snapshot builds from the sonatype snapshot repository by adding the following to your `repositories`:
```xml
<repository>
	<id>sonatype-nexus-snapshots</id>
	<name>Sonatype Nexus Snapshots</name>
	<url>https://oss.sonatype.org/content/repositories/snapshots/</url>
	<snapshots>
		<enabled>true</enabled>
	</snapshots>
	<releases>
		<enabled>false</enabled>
	</releases>
</repository>
```

## Building from source

    > git clone git@github.com:gservlet/gservlet-api.git
    > cd gservlet-api
    > mvn clean install


### Documentation

The documentation which is generated with Maven is based on [Asciidoctor](http://asciidoctor.org/). Only the HTML output is enabled.

    > mvn clean generate-resources -Pdocumentation

The built documentation can then be found in the following location:
  
    > ./target/generated-docs
    
On the other hand, the Javadocs can be found in the folder:

    > ./target/site/apidocs    

We use [UMLGraph](https://www.spinellis.gr/umlgraph/index.html) to generate UML class diagrams which are embedded in the Javadocs, therefore you must have [Graphviz](https://www.graphviz.org/) installed in your computer and the **GraphvizX.XX\bin** directory added to your system PATH.
