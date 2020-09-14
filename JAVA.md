# Building Java Codespaces

- use the Microsoft pre-built Java `.devcontainer` files as a template
- remove `node.js` if not needed
- remove `Maven` and/or `Gradle` if not needed
- review the base JDK image used - check version and file size


## Approaches to adding libraries

### #1 Include JAR
- use updated Java `.devcontainer` files as starting point
- publish JAR file to public location (GitHub, Cloud Storage, Maven Central...)
- update `DOCKERFILE` to include JAR file
- use when JAR file are over 100 MB (GitHub file size limit)
- create Codespace - test example code which uses JAR file
- TIP: you may have to `cd /` to **see** the files in your Codespaces container

### #2 Include Java source files
- use updated Java `.devcontainer` files as starting point
- include JAVA source files in GitHub Repo
- add JAR files to the `.classpath`
- select build process (i.e. `javac` or Maven, etc...)
- set `folder to include in Java project`
- get the source files to build
- create Codespace - test example code which uses built source files

## Enabling Java Tests
- install Java Test Runner VSCode Extention
- Get `junit.jar` and `haming.jar`, upload to your Repo
- add the two JAR files to your `.classpath`
- test with the Java Test extension (beaker)
- (optional) install and use Java Debugger extension
