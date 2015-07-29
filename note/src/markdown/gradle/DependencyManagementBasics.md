# Dependency Management Basics

## Basics

> dependency management: 
1. dependencies
2. publications

dependency resolution: download the dependencies of your project from a remote Maven or Ivy repository, or local, or another project.
transitive dependencies:  the dependencies of a project will themselves have dependencies.

## Declaring

build.gradle
```gradle
apply plugin: 'java'

repositories {
    mavenCentral()
}

dependencies {
    compile group: 'org.hibernate', name: 'hibernate-core', version: '3.6.7.Final'//External dependencies
    // for short:
    // compile 'org.hibernate:hibernate-core:3.6.7.Final'
    testCompile group: 'junit', name: 'junit', version: '4.+'
}
```

## Dependency configurations

In Gradle dependencies are grouped into configurations. A configuration is simply a named set of dependencies. We will refer to them as dependency configurations. 

a number of standard configurations defined by Java plugin:

*compile*

The dependencies required to compile the production source of the project.

*runtime*

The dependencies required by the production classes at runtime. By default, also includes the compile time dependencies.

*testCompile*

The dependencies required to compile the test source of the project. By default, also includes the compiled production classes and the compile time dependencies.

*testRuntime*

The dependencies required to run the tests. By default, also includes the compile, runtime and test compile dependencies.


## Repositories

Gradle looks for a dependency in the order they are specified, stopping at the first finding.

Maven central repository
```gradle
repositories {
    mavenCentral()
}
```

Remote Maven repository
```
repositories {
    maven {
        url "http://repo.mycompany.com/maven2"
    }
}
```

Remote Ivy repository
```
repositories {
    ivy {
        url "http://repo.mycompany.com/repo"
    }
}
```

Local Ivy directory
```
repositories {
    ivy {
        // URL can refer to a local directory
        url "../local-repo"
    }
}
```

## Publishing artifacts

example of publishing to a remote Ivy repository
```
uploadArchives {
    repositories {
        ivy {
            credentials {
                username "username"
                password "pw"
            }
            url "http://repo.mycompany.com"
        }
    }
}
```

example of publishing to a Maven repository
```
apply plugin: 'maven'

uploadArchives {
    repositories {
        mavenDeployer {
            repository(url: "file://localhost/tmp/myRepo/")
        }
    }
}
```