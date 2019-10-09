## A simple maven project

Firstly, you need to install maven, before you run maven command in terminal.
```
brew install maven
```
Secondly, create the folder structure.
```
src
    main
        java
            hello
```
> folder `hello` is the package name.

Finally, create the `pom.xml` file in the same level with folder `src`.

`<scope>` specify one of the following scop:

1. `compile`: That is, they should be available at compile time / runtime. (if you were building a WAR file, including in the /WEB-INF/libs folder of the WAR)
2. `provided`: Dependencies that are required for compiling the project code, but that will be provided at runtime by a container running the code
3. `test`: Dependencies that are used for compiling and running tests, but not required for building or running the project’s runtime code.

mvn commands:

1. `mvn compile`: This will run Maven, telling it to execute the compile goal. When it’s finished, you should find the compiled .class files in the target/classes directory.
2. `mvn package`: The package goal will compile your Java code, run any tests, and finish by packaging the code up in a JAR file within the target directory. The name of the JAR file will be based on the project’s `<artifactId>` and `<version>`. For example, given the minimal pom.xml file from before, the JAR file will be named gs-maven-0.1.0.jar.
3. `mvn install`: The install goal will compile, test, and package your project’s code and then copy it into the local dependency repository(~/.m2/repository), ready for another project to reference it as a dependency.
4. `mvn test`: Compiles and runs all classes in src/test/java with a name matching *Test. 
