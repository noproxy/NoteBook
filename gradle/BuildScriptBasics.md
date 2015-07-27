# Build Script Basics

## Projects and tasks

- Every Gradle build is made up of one or more projects.
- Each project is made up of one or more tasks.
  - A task represents some atomic piece of work which a build performs.

## Hello World
*Example:*

```
task hello {
    doLast {
        println 'Hello World!'
    }
}
```

*Execution:*
```
> gradle -q hello
```

## A shortcut task definition

```
task hello << {
    println 'Hello world!'
}
```

## Build scripts are code

```
task count << {
    4.times { print "$it " }
}
```

Outputs:

```
> gradle -q count
0 1 2 3
```

## Task dependencies

```
task hello << {
    println 'Hello world!'
}
task intro(dependsOn: hello) << {
    println "I'm Gradle"
}
```

Outputs:
```
> gradle -q intro
Hello world!
I'm Gradle
```

Lazy dependsOn: task hello is no need to declared before task intro.

*Please notice that you can't use shortcut notation when referring to a task that is not yet defined.*

## Dynamic Tasks

```
4.times { counter ->
    task "task$counter" << {
        println "I'm task number $counter"
    }
}
```

Outputs:
```
> gradle -q task1
I'm task number 1
```