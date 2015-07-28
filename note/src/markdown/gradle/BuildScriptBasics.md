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

## Manipulating existing task

### adding a dependency

```
4.times { counter ->
    task "task$counter" << {
        println "I'm task number $counter"
    }
}
task0.dependsOn task2, task3
```

Output:

```
> gradle -q task0
I'm task number 2
I'm task number 3
I'm task number 0
```

### adding behaviour

```
task hello << {
    println 'Hello Earth'
}
hello.doFirst {
    println 'Hello Venus'
}
hello.doLast {
    println 'Hello Mars'
}
hello << {
    println 'Hello Jupiter'
}
```

Output:

```
> gradle -q hello
Hello Venus
Hello Earth
Hello Mars
Hello Jupiter
```

## Shortcut notations

access an existing task

```
task hello << {
    println 'Hello world!'
}
hello.doLast {
    println "Greetings from the $hello.name task."
}
```

## Extra task properties

Add properties to a task

```
task myTask {
    ext.myProperty = "myValue"
}

task printTaskProperties << {
    println myTask.myProperty
}
```

## Using Ant Tasks

Example to execute Ant tasks and access Ant properties

```
task loadfile << {
    def files = file('../antLoadfileResources').listFiles().sort()
    files.each { File file ->
        if (file.isFile()) {
            ant.loadfile(srcFile: file, property: file.name)
            println " *** $file.name ***"
            println "${ant.properties[file.name]}"
        }
    }
}
```

Outputs:

```
> gradle -q loadfile
 *** agile.manifesto.txt ***
Individuals and interactions over processes and tools
Working software over comprehensive documentation
Customer collaboration  over contract negotiation
Responding to change over following a plan
 *** gradle.manifesto.txt ***
Make the impossible possible, make the possible easy and make the easy elegant.
(inspired by Moshe Feldenkrais)
```

## Using methods

```
task checksum << {
    fileList('../antLoadfileResources').each {File file ->
        ant.checksum(file: file, property: "cs_$file.name")
        println "$file.name Checksum: ${ant.properties["cs_$file.name"]}"
    }
}

task loadfile << {
    fileList('../antLoadfileResources').each {File file ->
        ant.loadfile(srcFile: file, property: file.name)
        println "I'm fond of $file.name"
    }
}

File[] fileList(String dir) {
    file(dir).listFiles({file -> file.isFile() } as FileFilter).sort()
}
```


## Default tasks

```
defaultTasks 'clean', 'run'
```

Then, call ```gradle -q``` will execute the default task

*This is equivalent to running gradle clean run. In a multi-project build every subproject can have its own specific default tasks. If a subproject does not specify default tasks, the default tasks of the parent project are used (if defined).*

## Configure by DAG

Gradle has a configuration phase and an execution phase. After the configuration phase, Gradle knows all tasks that should be executed. Gradle offers you a hook to make use of this information.

Example: Different outcomes of build depending on chosen tasks


```
task distribution << {
    println "We build the zip with version=$version"
}

task release(dependsOn: 'distribution') << {
    println 'We release now'
}

gradle.taskGraph.whenReady {taskGraph ->
    if (taskGraph.hasTask(release)) {
        version = '1.0'
    } else {
        version = '1.0-SNAPSHOT'
    }
}
```

Outputs of ```gradle -q distribution```

```
> gradle -q distribution
We build the zip with version=1.0-SNAPSHOT
```

Outputs of ```gradle -q release```

```
> gradle -q release
We build the zip with version=1.0
We release now
```

*whenReady affects the release task before the release task is executed. *