# JaCoCo Agent Demo

This project demonstrates how to use the JaCoCo Agent to measure code coverage in a Java application.

## What is JaCoCo Agent?

The JaCoCo Agent is a Java code coverage library agent that attaches to the JVM to monitor and collect data on code execution during runtime. It helps identify which parts of the code are tested and provides detailed coverage reports.

## Download

Download the JaCoCo Agent JAR file from the [JaCoCo GitHub Releases](https://github.com/jacoco/jacoco/releases).

## Setup Instructions

1. **Extract `jacocoagent.jar` and `jacococli.jar` from the latest zip release build** from [https://www.eclemma.org/jacoco/](https://www.eclemma.org/jacoco/).

2. **Build the Project**:

    ```bash
    mvn clean package
    ```

3. **Start the Application with the JaCoCo Agent**:

    ```bash
    java -javaagent:"jacocoagent.jar=destfile=target/jacoco.exec,append=false,includes=com.example.*" -jar target/demo-jacoco-agent-0.0.1-SNAPSHOT.jar
    ```

4. **Access the Application**:

   Open your browser and go to [http://localhost:8080/car](http://localhost:8080/car).

5. **Stop the Application**.

6. **Create the Coverage Report**:

    ```bash
    java -jar jacococli.jar report target/jacoco.exec --classfiles target/classes/com/example/ --sourcefiles src/main/java/ --html target/
    ```

   This command will generate an HTML report in the `target` directory.
