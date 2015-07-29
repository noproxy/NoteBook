# Groovy Quickstart

1. Use Groovy plugin ```apply plugin: 'groovy'```, this extends the Java plugin. You project can contain Groovy source code, Java source code, or a mix of the two.
 
> ```compile``` Task look sources files in src/main/groovy

> ```compileTest``` Task look sources files in src/test/groovy

2. These directories can contain a mixture of Java and Groovy source files.
3. add a dependency of Groovy libraries to the groovy configuration

```gradle 
repositories {
    mavenCentral()
}

dependencies {
    compile 'org.codehaus.groovy:groovy-all:2.3.10'
}
```

4. Because a Groovy project is a Java project, whatever you can do with a Java project, you can also do with a Groovy project.