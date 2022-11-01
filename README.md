# :uk: Spring Boot :wrench: Basic setup

## About Spring Boot

[Spring Boot](https://spring.io/projects/spring-boot) allows you to create stand-alone Spring applications by embedding an application server.

It provides production-ready features like metrics or health-checks and simplifies the build configuration overall.

In this example you can check how to simply build and run a Spring Boot application with the basics.

## Technical requirements

You are going to need only 2 things

- [Maven](https://maven.apache.org/) - _for project management_
- [JDK](https://www.oracle.com/java/technologies/downloads) - _this is example is built on version 18_

## How to configure Spring Boot

- Create a new project and add your [pom.xml](pom.xml) with the required dependencies and plugins
  - spring-boot-starter-web - _to start the application context up and its web resources_
  - spring-boot-starter-test - _as we will be adding a test to check that the application context starts_
  - spring-boot-maven-plugin - _a Spring's Maven plugin to compile the project as a stand-alone JAR_
  - maven-surefire-plugin - _a Maven's plugin to run the tests upon packaging_
- Add the [application.properties](src/main/resources/application.properties) to optionally specify a context's path for the application if you want your application to start on _localhost:8080/{your_path}_
- Create a Java class such as [SpringBootBasicSetup.java](src/main/java/com/codewithhades/springboot/basicsetup/SpringBootBasicSetup.java) with a main method that starts the Spring application. Annotate this class with @SpringBootApplication in order to provide the entry point of the application
  ````java
  @SpringBootApplication
  public class SpringBootBasicSetup {
      public static void main(String[] args) {
          SpringApplication.run(SpringBootBasicSetup.class, args);
      }
  }
  ````
- Add a [SpringBootBasicSetupTest.java](src/test/java/com/codewithhades/springboot/basicsetup/SpringBootBasicSetupTest.java) to test that the application starts properly

## How to start the Spring boot application

You have 3 different ways of starting your Spring Boot application
- Simply run your main method located at [SpringBootBasicSetup.java](src/main/java/com/codewithhades/springboot/basicsetup/SpringBootBasicSetup.java) from your IDE
- Use Maven to package the JAR (and run the test), and then run the JAR with Java from a console
  ````bash
  mvn clean package
  java -jar target/basic-setup.jar
  ````
- Call the Maven plugin from a console
    ````bash
  mvn spring-boot:run
  ````
After starting the application and browsing **localhost:8080/app** you should be able to see a _Whitelabel Error Page_ with a 404 status. Fear not! Your application is running but there are no web resources nor APIs mapped for that path.

I hope you found this example useful and if you want to keep learning something about Spring Boot you can check this example where we deploy a [Spring Boot REST API](https://github.com/codewithhades/spring-boot-api).

:coffee: May Java be with you!