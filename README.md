# :uk: Spring Boot :wrench: Basic setup

## About this example

[Spring Boot](https://spring.io/projects/spring-boot) allows you to create stand-alone Spring applications by embedding an application server.

It provides production-ready features like metrics or health-checks and simplifies the build configuration overall.

In this example you can check how to build and run a Spring Boot application with the basics.

## Requirements

- [Maven](https://maven.apache.org/) - _for project management_
- [JDK](https://www.oracle.com/java/technologies/downloads) - _this is example is built on version 18_

## How to build it

- Create a new project and add your [pom.xml](pom.xml) with the required dependencies and plugins
  - spring-boot-starter-web - _to start the application context up and its web resources_
  - spring-boot-starter-test - _as we will be adding a test to check that the application context starts_
  - spring-boot-maven-plugin - _a Spring's Maven plugin to compile the project as a stand-alone JAR_
  - maven-surefire-plugin - _a Maven's plugin to run the tests upon packaging_
- Add the [application.properties](src/main/resources/application.properties) to optionally specify a context's path for the application if you want your application to start on _localhost:8080/{your_path}_
- Create a Java class such as [SpringBootBasicSetupApp.java](src/main/java/com/codewithhades/springboot/basicsetup/SpringBootBasicSetupApp.java) with a main method that starts the Spring application. Annotate this class with @SpringBootApplication in order to provide the entry point of the application
  ````java
  @SpringBootApplication
  public class SpringBootBasicSetupApp {
      public static void main(String[] args) {
          SpringApplication.run(SpringBootBasicSetupApp.class, args);
      }
  }
  ````
- Optionally create a [SpringBootBasicSetupAppTest.java](src/test/java/com/codewithhades/springboot/basicsetup/SpringBootBasicSetupAppTest.java) to test that the application starts properly

## How to run it

You have 3 different ways of starting your Spring Boot application
- Simply run your main method located at [SpringBootBasicSetupApp.java](src/main/java/com/codewithhades/springboot/basicsetup/SpringBootBasicSetupApp.java) from your IDE
- Use Maven to package the JAR and run it with Java from a console
  ````bash
  mvn clean package
  java -jar target/basic-setup.jar
  ````
- Call the Maven plugin from a console
    ````bash
  mvn spring-boot:run
  ````
After starting the application and browsing **localhost:8080/app** you should be able to see a _Whitelabel Error Page_ with a 404 status. Fear not! Your application is running but there are no web resources nor APIs mapped for that path.

I hope you found useful this example and if you now want to go a bit further I can suggest you that you check an example of a [Spring Boot with an API](https://github.com/codewithhades/spring-boot-api).

:coffee: May Java be with you!


---

# :es: Spring Boot :wrench: Configuración básica

## Acerca de este proyecto

[Spring Boot](https://spring.io/projects/spring-boot) te ofrece la posibilidad de crear aplicaciones Spring que son independientes al contener embebido un servidor de aplicaciones.

Proporciona herramientas listas para producción como métricas o health-checks, y simplifica la configuración en general.

En este ejemplo podrás ver cómo construir y arrancar una aplicación Spring Boot con lo básico.

## Requisitos

- [Maven](https://maven.apache.org/) - _para la gestión del proyecto_
- [JDK](https://www.oracle.com/java/technologies/downloads) - _este ejemplo está construido en la versión 18_

## Cómo construirlo

- Crea un nuevo proyecto y añade tu [pom.xml](pom.xml) con las dependencias y plugins que necesitarás
  - spring-boot-starter-web - _para arrancar el contexto y sus recursos web_
  - spring-boot-starter-test - _ya que añadiremos un test para comprobar que el contexto de la aplicación arranca_
  - spring-boot-maven-plugin - _un plugin para Maven de Spring para compilar el proyecto como un JAR independiente_
  - maven-surefire-plugin - _un plugin de Maven para ejecutar los tests al empaquetar el proyecto_
- Añade el [application.properties](src/main/resources/application.properties) para opcionalmente especificar una dirección del contexto y arrancar tu aplicación en _localhost:8080/{your_path}_
- Crea una clase Java tal como [SpringBootBasicSetupApp.java](src/main/java/com/codewithhades/springboot/basicsetup/SpringBootBasicSetupApp.java) con un método main que arranque la aplicación Spring. Anota esta clase con @SpringBootApplication para proveer un punto de entrada de la aplicación
  ````java
  @SpringBootApplication
  public class SpringBootBasicSetupApp {
      public static void main(String[] args) {
          SpringApplication.run(SpringBootBasicSetupApp.class, args);
      }
  }
  ````
- Opcionalmente crea un [SpringBootBasicSetupAppTest.java](src/test/java/com/codewithhades/springboot/basicsetup/SpringBootBasicSetupAppTest.java) para corroborar que la aplicación arranca correctamente

## Cómo arrancarlo

Tienes 3 diferentes maneras de arrancar tu aplicación Spring Boot
- Simplemente arranca el método main localizado en [SpringBootBasicSetupApp.java](src/main/java/com/codewithhades/springboot/basicsetup/SpringBootBasicSetupApp.java) desde tu IDE
- Usa Maven para construir el JAR y lanzarlo con Java desde una consola
  ````bash
  mvn clean package
  java -jar target/basic-setup.jar
  ````
- Ejecuta el plugin de Maven desde una consola
    ````bash
  mvn spring-boot:run
  ````
Después de arrancar la aplicación y navegar a **localhost:8080/app** deberías poder ver un _Whitelabel Error Page_ con un estado 404. ¡No temas! Tu aplicación está arrancada pero no hay recursos web ni APIs mapeados para esa localización.

Espero que te haya sido útil este ejemplo, y si quieres ir un poco más lejos te recomiendo echarle un vistazo a este ejemplo de una aplicación [Spring Boot con una API](https://github.com/codewithhades/spring-boot-api).

¡Que Java te acompañe!