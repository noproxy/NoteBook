# NoteBook
My NoteBook managed by Git and Gradle.

# Build

Execute

```
gradle build
```
To generate html, execute

```
gradle markdownToHtml
```


## Import into IDE

### Intellij IDEA/Android Studio

execute ```gradle idea``` under root project, then directly open this project from IDEA or android studio.

### Eclipse


Add ```apply plugin: 'eclipse'``` to all projects:

```
allprojects {
    apply plugin: 'eclipse'
}
```

Then, execute ```gradle eclipse``` under root project, then directly open this project from eclipse.
