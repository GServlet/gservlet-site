---
title: "Getting Started"
chapter : true
weight: 1
pre : "<b>1. </b>"
---

# Getting Started

To get started with GServlet, you may want to begin by creating your first project. This section shows you how to get up and running quickly. It is highly recommended to consume the API through a dependency management tool and the artifact can be found in Maven's central repository. it is named _gservlet-api_ and you just need to name a dependency on it in your project. We version the project by following [Semantic Versioning](https://semver.org), which is a general template that everyone uses and understands. The current release is 1.0.0.

{{% notice note %}}
If you have a prior experience with the Servlet API, creating your first web application with GServlet will feel like a breeze.  
{{% /notice %}}


## Installation

### Maven

```xml
<dependency>
	<groupId>org.gservlet</groupId>
	<artifactId>gservlet-api</artifactId>
	<version>1.0.0</version>
</dependency>
```

### Gradle

```
repositories {
    mavenCentral()
}

dependencies {
    compile("org.gservlet:gservlet-api:1.0.0")
}
```

## Running Your First Groovy Servlet

Once your Java web server is installed and configured, you can put it to work. Five steps take you from writing your first Groovy servlet to running it. These steps are as follows:

1. Create a dynamic web project
* Create the scripts folder inside your web content directory
* Write the servlet source code
* Run your Java web server
* Call your servlet from a web browser


Below are some examples that you can try out and for a hot reloading of your source code, set the **GSERVLET_RELOAD** environment variable to true in your IDE. 
    
#### ProjectServlet.groovy

``` java
import org.gservlet.annotation.Servlet

@Servlet("/projects")
import org.gservlet.annotation.Servlet

@Servlet("/projects")
class ProjectServlet {

	def projects = []

	void init() {
	   projects << [id : 1, name : "Groovy", url : "https://groovy-lang.org"]
	   projects << [id : 2, name : "Spring", url : "https://spring.io"]
	   projects << [id : 3, name : "Maven",  url : "https://maven.apache.org"]
	}

	void get() {
	   json(projects)
	}

	void post() {
	   def project = request.body
	   projects << project
	   json(project)
	}

	void put() {
	   def project = request.body
	   int index = projects.findIndexOf { it.id == project.id }
	   projects[index] = project
	   json(project)
	}

	void delete() {
	   def project = request.body
	   int index = projects.findIndexOf { it.id == project.id }
	   json(projects.remove(index))
	}

}
```

#### CorsFilter.groovy

``` java
import org.gservlet.annotation.Filter

@Filter("/*")
class CorsFilter {

    void filter() {
      response.addHeader("Access-Control-Allow-Origin", "*")
      response.addHeader("Access-Control-Allow-Methods","GET, OPTIONS, HEAD, PUT, POST, DELETE")
      if (request.method == "OPTIONS") {
        response.status = response.SC_ACCEPTED
        return
      }
      next()
    }

}
```

#### ServletRequestListener.groovy

``` java 
import org.gservlet.annotation.RequestListener

@RequestListener
class ServletRequestListener {

   void init() {
     println "request initialized"
   }

   void destroy() {
     println "request destroyed"
   }

}
```

For a deep insight, please read the Developer Guide in our [documentation](/documentation) page. 
