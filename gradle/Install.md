# Installing Gradle

## Prerequisites

- JRE/JDK 6+
- NO need for Groovy( any existing installation is ignored)

## Environment variables

add GRADLE_HOME/bin to PATH

## Testing

run ```gradle -v```

## JVM options

- set via environment variables:

   ```GRADLE_OPTS``` or ```JAVA_OPTS```, or both

> A typical use case would be to set the HTTP proxy in JAVA_OPTS and the memory options in GRADLE_OPTS. Those variables can also be set at the beginning of the gradle or gradlew
script.

- unable via command line yer

