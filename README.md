# Spock+RestAssured+Allure

Template framework for API and UI automated testing. It already contains all the necessary dependencies, so you can start using this stack right away.

# Technical Stack

* Language: [Groovy](https://groovy-lang.org/)
* Testing Framework: [Spock](https://spockframework.org/)
* API Testing Library: [RestAssured](https://rest-assured.io/)
* UI Testing Library: [Selenide](https://selenide.org/)
* Report: [Allure](https://allurereport.org/)
* Build Tool: [Maven](https://maven.apache.org/) or [Gradle](https://gradle.org/)

# Prerequisites

1. This project is using Java 17, so make sure to use correct Java version both locally an in IDE.
   - Setup Java version in Intellij IDEA: File -> Project Structure... -> Project Settings -> Project -> SDK -> choose 17.
   
3. Choose one of the build tools that you want to use and delete the other one. It doesn't affect the functionality, but it's just more clean and reliable approach to leave only functionality that is used in the project.  
    - If you want to use Maven, then delete Gradle files and mentions:
        - delete `gradle/wrapper`
        - delete `build.gradle.kts`
        - delete `gradlew`
        - delete `gradlew.bat`
        - delete `settings.gradle.kts`
        - delete "Run Tests With Gradle" and "Generate Local Report With Gradle" sections in `README.md`
        - delete "# Gradle" rows in `.gitignore`
    - If you choose to use Gradle, then delete all Maven mentions:
        - delete `.mvn/wrapper`
        - delete `mvnw`
        - delete `mvnw.cmd`
        - delete "Run Tests With Maven" and "Generate Local Report With Maven" sections in `README.md`
        - delete "# Maven" rows in `.gitignore`

# Running Tests

You can use either Maven or Gradle to run the tests in this project.

## Run Tests With Maven

```shell
./mvnw clean test
```

## Run Tests With Gradle

```shell
./gradlew clean test
```

# Allure Report

## Generate Local Report With Maven

Note: On Windows, running this command may cause the report serving processes to leak. For more details, check [this issue](https://github.com/allure-framework/allure-java/issues/836).

```shell
./mvnw allure:serve
```

## Generate Local Report With Gradle

```shell
./gradlew allureServe
```
