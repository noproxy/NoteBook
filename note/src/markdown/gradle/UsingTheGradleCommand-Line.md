# Using the Gradle Command-Line

## Executing multiple tasks

```gradle compile test``` will execute the compile and test tasks in the order that they are listed on the command-line.

But each task is executed only once, if the multiple tasks have the same dependencies, them will be execute only once.
For example, ```gradle test test``` is exactly the same as gradle test.

## Excluding tasks

```gradle dist -x test``` to execute dist but test task.

## Continuing the build when a failure occurs

``` --continue```

Each of the encountered failures will be reported at the end of the build.

## Task name abbreviation

You only need to provide enough of the task name to uniquely identify the task. In a camel case task name is ok.

```
gradle compTest
gradle cT
```

## Selecting build file/directory

```-b``` option to select build file, and ignore the ```settings.gradle```

```-p``` option to select specify the project directory to use. It can be use to select a the subproject.

## More information about build

Use *project report plugin*

- Run ```gradle projects``` to list projects hierarchy and their description(add by ```description = 'this is a description'``` ).

- Run ```gradle tasks``` to list main tasks and their description of the selected project. By default, this report shows only those tasks which have been assigned to a task group. Use ```--all``` to list all.






