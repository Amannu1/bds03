# Bds03

![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring](https://img.shields.io/badge/spring-%236DB33F.svg?style=for-the-badge&logo=spring&logoColor=white)
![JUnit5](https://img.shields.io/badge/JUnit5-f5f5f5?style=for-the-badge&logo=junit5&logoColor=dc524a)

This project is a Test-Driven Development (TDD) initiative built with **Java Spring Boot, JUnit 5, H2 Console and Spring Security for authentication control** focusing on department processes and employee management.

The project ensures that all core functionalities developed and validated through automated tests before implementation.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Tests](#tests)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Amannu1/bds03
```
2. Install dependencies with Maven

## Usage

1. Start the application with Maven
2. The API will be accessible at http://localhost:8080
3. Right click test/java directory
4. Run all tests

## API Endpoints
The API provides the following endpoints:

```markdown
GET /departments - Retrieve a list of all departments. (ADMIN and OPERATOR access required.)

GET /employees - Retrieve a list of all employees. (ADMIN and OPERATOR access required.)

POST /employees - Register a new employer. (ADMIN access required)
```

## Tests

The tests cover the following scenarios:

### Department

- findAll should return all resources sorted by name when admin logged
- findAll should return all resources sorted by name when employee logged
- findAll should return 401 when no user logged

### Employer

- insert should return 403 when operator logged
- insert should return 401 when no user logged
- insert should insert resource when admin logged and correct data
- insert should return 422 when admin logged and blank name
- insert should return 422 when admin logged and invalid email
- insert should return 422 when admin logged and null department
