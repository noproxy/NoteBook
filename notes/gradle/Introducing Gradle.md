#Introducing Gradle

@(Gradle)[gradle|Book|build]

Gradle is the next-generation build automation, also a **Groovy DSL**.

-------------

##Good

Gradle provides support for Java, Groovy, Scala, Web, and OSGi projects, out of
the box.

- Support for Ant tasks, Ivy and Maven repositories;
- Incremental builds;
- Multi-project builds;
- The Gradle wrapper allows us to execute Gradle builds, even though Gradle is not installed on a computer.

##Install
Gradle requires JDK 5 or higher, but don't have to install Groovy. Gradle bundles the Groovy libraries with the distribution and will ignore a Groovy installation already available on our computer.
if installed success, run
    $gradle -v
---------

    (print "hello world")




>**Tip:** A directory named init.d where we can store Gradle scripts that need to be executed each time we run Gradle.

##File
file [main]

[main]:../../src/Main.clj