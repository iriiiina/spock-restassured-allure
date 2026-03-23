# CLAUDE.md

## Project Overview

Template framework for automated API and UI testing using Groovy + Spock + RestAssured + Allure.
Tests run against JSONPlaceholder API (`https://jsonplaceholder.typicode.com`).

## Tech Stack

- **Language**: Groovy 4.x on Java 17
- **Test Framework**: Spock 2.3
- **API Testing**: RestAssured 5.x
- **UI Testing**: Selenide 6.19
- **Reporting**: Allure 2.24
- **Build**: Both Gradle (8.10.2) and Maven (3.9.3) via wrappers

## Build & Test Commands

```bash
# Gradle
./gradlew clean test
./gradlew allureServe          # open Allure report

# Maven
./mvnw clean test
./mvnw allure:serve            # open Allure report
```

## Project Structure

```
src/main/groovy/
  BeforeAll.groovy       # Global setup: RestAssured filters, Selenide config
  Spec.groovy            # Abstract base class (extends Specification), holds base URL
  Steps.groovy           # API step methods with @Step annotations
  Requirement.groovy     # Custom annotation combining @Story + @TmsLink

src/test/groovy/
  UsersTest.groovy       # API tests for /users endpoints
  PostsTest.groovy       # API tests for /posts endpoints
  E2ETest.groovy         # UI tests using Selenide
  resources/allure.properties  # Allure link patterns
```

## Code Conventions

- All test classes extend `Spec` and use `*Test` suffix
- Spock BDD blocks: `given:` / `when:` / `then:` / `where:`
- Data-driven tests use Spock's `where:` table syntax
- RestAssured fluent chain: `given()...when()...then()`
- Allure annotations: `@Epic`, `@Feature`, `@Story`, `@Step`, `@Issue`, `@Link`
- Step methods live in `Steps.groovy` as static methods
- Groovy idioms: implicit returns, string interpolation, closure syntax
- Formatting: 4-space indent, LF line endings, 120 char max line length (see .editorconfig)

## CI

GitHub Actions (`.github/workflows/run-tests.yml`): runs on PRs to `master`, parallel Gradle + Maven jobs, JDK 17 Temurin + Chrome, reports via `dorny/test-reporter`.

## Key Patterns

- `BeforeAll` is instantiated once as a static field in `Spec` — configures RestAssured logging filters and Selenide browser settings (1920x1080, 10s timeout)
- `Spec.url` holds the base API URL used across all tests
- Custom `@Requirement` annotation composes `@Story` + `@TmsLink` for traceability
