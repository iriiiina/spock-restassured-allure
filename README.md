# Spock+RestAssured+Allure

Template framework for API and UI automated testing. It already contains all the necessary dependencies, so you can start using this stack right away.

## Technical Stack

* Language: [Groovy](https://groovy-lang.org/)
* Testing Framework: [Spock](https://spockframework.org/)
* API Testing Library: [RestAssured](https://rest-assured.io/)
* UI Testing Library: [Selenide](https://selenide.org/)
* Report: [Allure](https://allurereport.org/)
* Build Tool: [Maven](https://maven.apache.org/) or [Gradle](https://gradle.org/)

## Running Tests

You can use either Maven or Gradle to run the tests in this project.

**Run Tests With Maven:**

```shell
./mvnw clean test
```

**Run Tests With Gradle:**

```shell
./gradlew clean test
```

## Allure Report

The final Allure report is located in [gh-pages](https://github.com/karltiirik/spock-restassured-allure/tree/gh-pages) branch and is available in a browser here: [https://karltiirik.github.io/spock-restassured-allure](https://karltiirik.github.io/spock-restassured-allure).

**Generate Local Report With Maven:**

Note: On Windows, running this command may cause the report serving processes to leak. For more details, check [this issue](https://github.com/allure-framework/allure-java/issues/836).

```shell
./mvnw allure:serve
```

**Generate Local Report With Gradle:**

```shell
./gradlew allureServe
```
