# Java Quickstart

## Basic

build.gradle
```
apply plugin: 'java'
```

 - src/main/java: sources
 - src/test/java: test source
 - src/main/resources: JAR file as resources
 - src/test/resources: included in the classpath used to run the tests
 - build: all output files
 - build/libs: JAR output


 Use ```gradle properties``` to list the properties of a project
 Use ```gradle tasks``` to list the tasks of a project

Some useful task:

- clean: Deletes the build directory, removing all built files.
- assemble: Compiles and jars your code, but does not run the unit tests. Other plugins add more artifacts to this task. For example, if you use the War plugin, this task will
also build the WAR file for your project.
- check: Compiles and tests your code. Other plugins add more checks to this task. For example, if you use the checkstyle plugin, this task will also run Checkstyle against your
source code.

Publish JAR file

example publish to local:

```
uploadArchives {
    repositories {
       flatDir {
           dirs 'repos'
       }
    }
}
```

then run ```gradle uploadArchives```

## Multi-project Java build

### Define

this is a project tree:
```
multiproject/
  api/
  services/webservice/
  shared/
  services/shared/
```

settings.gradle

```
include "shared", "api", "services:webservice", "services:shared"
```

### Common configuration

build.gradle
```
subprojects {
    apply plugin: 'java'
    apply plugin: 'eclipse-wtp'

    repositories {
       mavenCentral()
    }

    dependencies {
        testCompile 'junit:junit:4.12'
    }

    version = '1.0'

    jar {
        manifest.attributes provider: 'gradle'
    }
}
```

This apply to all subproject *but not to the root project*.


### Dependencies between projects

api/build.gradle
```
dependencies {
    compile project(':shared')
}
```

### Creating a distribution

example distribution file

api/build.gradle
```
task dist(type: Zip) {
    dependsOn spiJar
    from 'src/dist'
    into('libs') {
        from spiJar.archivePath
        from configurations.runtime
    }
}

artifacts {
   archives dist
}
```