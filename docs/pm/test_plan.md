---
layout: default
title: Test plan
nav_order: 3
parent: Project management
---
# Test Plan

## Table of contents

- [1. Introduction](#1-introduction)
  * [1.1 Purpose](#11-purpose)
  * [1.2 Scope](#12-scope)
  * [1.3 Intended Audience](#13-intended-audience)
  * [1.4 Document Terminology and Acronyms](#14-document-terminology-and-acronyms)
  * [1.5  References](#15--references)
  * [1.6 Document Structure](#16-document-structure)
- [2. Evaluation Mission and Test Motivation](#2-evaluation-mission-and-test-motivation)
  * [2.1 Background](#21-background)
  * [2.2 Evaluation Mission](#22-evaluation-mission)
  * [2.3 Test Motivators](#23-test-motivators)
- [3. Target Test Items](#3-target-test-items)
- [4. Outline of Planned Tests](#4-outline-of-planned-tests)
  * [4.1 Outline of Test Inclusions](#41-outline-of-test-inclusions)
  * [4.2 Outline of Other Candidates for Potential Inclusion](#42-outline-of-other-candidates-for-potential-inclusion)
  * [4.3 Outline of Test Exclusions](#43-outline-of-test-exclusions)
- [5. Test Approach](#5-test-approach)
  * [5.1 Initial Test-Idea Catalogs and Other Reference Sources](#51-initial-test-idea-catalogs-and-other-reference-sources)
  * [5.2 Testing Techniques and Types](#52-testing-techniques-and-types)
    + [5.2.1 Data and Database Integrity Testing](#521-data-and-database-integrity-testing)
    + [5.2.2 Functional Testing](#522-functional-testing)
    + [5.2.3 Business Cycle Testing](#523-business-cycle-testing)
    + [5.2.4 User Interface Testing](#524-user-interface-testing)
    + [5.2.5 Performance Profiling](#525-performance-profiling)
    + [5.2.6 Load Testing](#526-load-testing)
    + [5.2.7 Stress Testing](#527-stress-testing)
    + [5.2.8 Volume Testing](#528-volume-testing)
    + [5.2.9 Security and Access Control Testing](#529-security-and-access-control-testing)
    + [5.2.10 Failover and Recovery Testing](#5210-failover-and-recovery-testing)
    + [5.2.11 Configuration Testing](#5211-configuration-testing)
    + [5.2.12 Installation Testing](#5212-installation-testing)
- [6. Entry and Exit Criteria](#6-entry-and-exit-criteria)
  * [6.1 Test Plan](#61-test-plan)
    + [6.1.1 Test Plan Entry Criteria](#611-test-plan-entry-criteria)
    + [6.1.2 Test Plan Exit Criteria](#612-test-plan-exit-criteria)
    + [6.1.3 Suspension and Resumption Criteria](#613-suspension-and-resumption-criteria)
  * [6.2 Test Cycles](#62-test-cycles)
      - [6.2.1 Test Cycle Entry Criteria](#621-test-cycle-entry-criteria)
      - [6.2.2 Test Cycle Exit Criteria](#622-test-cycle-exit-criteria)
      - [6.2.3 Test Cycle Abnormal Termination](#623-test-cycle-abnormal-termination)
- [7. Deliverables](#7-deliverables)
- [7.1 Test Evaluation Summaries](#71-test-evaluation-summaries)
- [7.2 Reporting on Test Coverage](#72-reporting-on-test-coverage)
- [7.3 Perceived Quality Reports](#73-perceived-quality-reports)
- [7.4 Incident Logs and Change Requests](#74-incident-logs-and-change-requests)
- [7.5 Smoke Test Suite and Supporting Test Scripts](#75-smoke-test-suite-and-supporting-test-scripts)
- [7.6      Additional Work Products](#76------additional-work-products)
  * [7.6.1     Detailed Test Results](#761-----detailed-test-results)
  * [7.6.2     Additional Automated Functional Test Scripts](#762-----additional-automated-functional-test-scripts)
  * [7.6.3     Test Guidelines](#763-----test-guidelines)
  * [7.6.4     Traceability Matrices](#764-----traceability-matrices)
- [8. Testing Workflow](#8-testing-workflow)
- [9. Environmental Needs](#9-environmental-needs)
  * [9.1 Base System Hardware](#91-base-system-hardware)
  * [9.2 Base Software Elements in the Test Environment](#92-base-software-elements-in-the-test-environment)
  * [9.3 Productivity and Support Tools](#93-productivity-and-support-tools)
  * [9.4 Test Environment Configurations](#94-test-environment-configurations)
- [10. Responsibilities, Staffing, and Training Needs](#10-responsibilities--staffing--and-training-needs)
  * [10.1 People and Roles](#101-people-and-roles)
  * [10.2 Staffing and Training Needs](#102-staffing-and-training-needs)
- [11. Iteration Milestones](#11-iteration-milestones)
- [12. Risks, Dependencies, Assumptions, and Constraints](#12-risks--dependencies--assumptions--and-constraints)
- [13. Management Process and Procedures](#13-management-process-and-procedures)

## 1. Introduction

### 1.1 Purpose

The purpose of the Iteration Test Plan is to gather all of the information necessary to plan and control the test effort for a given iteration. It describes the approach to testing the software.
This Test Plan for Vaultionizer supports the following objectives:

- Identifies the items that should be targeted by the tests.
- Identifies the motivation for and ideas behind the test areas to be covered.
- Outlines the testing approach that will be used.
- Identifies the required resources and provides an estimate of the test efforts.

### 1.2 Scope

This documents conatins the implemented tests of the Vaultionizer project. The Vaultionizer project contains Unit Tests, Integration Tests and Acceptance Tests. The majority of these tests are executed automatically.

### 1.3 Intended Audience

This document is intended for internal documentation and overview over the testing enviroment. This is a living document with the intend of been completed at the end of the fourth semester.

### 1.4 Document Terminology and Acronyms

| Abbr | Abbreviation                        |
|------|-------------------------------------|
| API  | Application Programmable Interface  |
| CI   | Continuous Integration              |
| CD   | Continuous Delivery/Deployment      |
| n/a  | not applicable                      |
| SRS  | Software Requirements Specification |
| tbd  | to be determined                    |
| UI   | User Interface                      |
| VC   | Version Control                     |
| TDD  | Test Driven Development             |

### 1.5  References

| Title                                                                   | Date       | Publishing organization   |
| ------------------------------------------------------------------------|:----------:| ------------------------- |
| [Blog](https://vaultionizer.com/)                                       | Mai. 2021  | Vaultionizer              |
| [GitHub Repository](https://github.com/Vaultionizer)                    | Mai. 2021  | Vaultionizer              |
| [UC Create Space](./use_cases/uc_create_space.md)                      | Mai. 2021  | Vaultionizer              |   
| [UC Delete Space](./use_cases/uc_delete_space.md)                      | Mai. 2021  | Vaultionizer              |    
| [UC Delete User](./use_cases/uc_delete_user.md)                        | Mai. 2021  | Vaultionizer              |    
| [UC Download File](./use_cases/uc_download_file.md)                    | Mai. 2021  | Vaultionizer              |    
| [UC Encrypt](./use_cases/uc_encrypt.md)                                | Mai. 2021  | Vaultionizer              |    
| [UC Show file](./use_cases/uc_show_file_structure.md)                   | Mai. 2021  | Vaultionizer              |    
| [UC Upload File](./use_cases/uc_upload_file.md)                                 | Mai. 2021  | Vaultionizer              |   
| [Test Plan](./TestPlan.md)                                              | Mai. 2021  | Vaultionizer              |
| [SRS](./srs.md)                                                         | Mai. 2021  | Vaultionizer              |
| [SAD](./sad.md)                                                         | Mai. 2021  | Vaultionizer              |

### 1.6 Document Structure

See table og contents.

## 2. Evaluation Mission and Test Motivation

### 2.1 Background

Testing serves to ensure that the written code does what it is intended to do. It also prevents future code changes to break existing functionality unnoticed. 

### 2.2 Evaluation Mission

The goals of testing is the improve the security and functionality of the project. Therefore the tests are focused on reporting issues with functionality and security of larger code blocks.

### 2.3 Test Motivators

These test support the effort of better security, less bugs and faster development.

## 3. Target Test Items

The listing below identifies those test items software, hardware, and supporting product elements that have been identified as targets for testing. This list represents what items will be tested.

- Spring Boot Backend
- Android Client Frontend

## 4. Outline of Planned Tests

### 4.1 Outline of Test Inclusions

*Frontend: Android Client*:

- UI testing of views/fragments
- Unit testing

*Backend: Spring Boot Application*:

- Unit testing
- Integration testing
- Api testing

The tests themselves will not be tested and will not account into code coverage.

### 4.2 Outline of Other Candidates for Potential Inclusion

n/a

### 4.3 Outline of Test Exclusions

n/a

## 5. Test Approach


### 5.1 Initial Test-Idea Catalogs and Other Reference Sources

n/a

### 5.2 Testing Techniques and Types

#### 5.2.1 Data and Database Integrity Testing

n/a

#### 5.2.2 Functional Testing

| Unit Tests            | Description                                                                             |
|-----------------------|-----------------------------------------------------------------------------------------|
|Technique Objective    |  Test basic functionality of single components.                                         |
|Technique              |  JUnit4 Tests                                                                           |
|Oracles                |  Checks asserted output of a basic function against the output of the implementation.   |
|Required Tools         |  JUnit4                                                                                 |
|Success Criteria       |  The asserted output is identical to the generated output.                              |
|Special Considerations |  Random generation of inputs must be expected when handling cryptographic instructions. |

#### 5.2.3 Business Cycle Testing

n/a

#### 5.2.4 User Interface Testing

| UI Tests              | Description                                                         |
|-----------------------|---------------------------------------------------------------------|
|Technique Objective    | Simulation of UI interaction.                                       |
|Technique              | UI Tests                                                            |
|Oracles                | Interactions with UI components through touch screen input.         |
|Required Tools         | Espresso                                                            |
|Success Criteria       | All tests pass with the intended result.                            |
|Special Considerations | -                                                                   |

#### 5.2.5 Performance Profiling

n/a

#### 5.2.6 Load Testing

n/a

#### 5.2.7 Stress Testing

| Cucumber Tests        | Description                                                         |
|-----------------------|---------------------------------------------------------------------|
|Technique Objective    | Stress testing the API.                                             |
|Technique              | Exceptions handling                                                 |
|Oracles                | Test exception handling by sending corrupt request to the API.      |
|Required Tools         | Cucumber & database                                                 |
|Success Criteria       | API deals with corrupt request as intended.                         |
|Special Considerations | -                                                                   |


#### 5.2.8 Volume Testing

n/a

#### 5.2.9 Security and Access Control Testing

| Cucumber Tests        | Description                                                         |
|-----------------------|---------------------------------------------------------------------|
|Technique Objective    | Test the permissions of users.                                      |
|Technique              | Permission checks for membership inside a space.                    |
|Oracles                | Check the permissions of a user for a given object.                 |
|Required Tools         | Cucumber & database                                                 |
|Success Criteria       | The user has the expected permissions (nothing more/less)           |
|Special Considerations | -                                                                   |


#### 5.2.10 Failover and Recovery Testing

n/a


#### 5.2.11 Configuration Testing

n/a


#### 5.2.12 Installation Testing

| GitHub Actions        | Description                                                                    |
|-----------------------|--------------------------------------------------------------------------------|
|Technique Objective    | Checks if the application is building and installing correctly after a update. |
|Technique              | GitHub Actions                                                                 |
|Oracles                | The apps is installed on a universal device.                                   |
|Required Tools         | GitHub                                                                         |
|Success Criteria       | Build and installation is successful.                                          |
|Special Considerations | -                                                                              |


## 6. Entry and Exit Criteria

### 6.1 Test Plan

#### 6.1.1 Test Plan Entry Criteria

n/a

#### 6.1.2 Test Plan Exit Criteria

n/a

#### 6.1.3 Suspension and Resumption Criteria

n/a

### 6.2 Test Cycles

##### 6.2.1 Test Cycle Entry Criteria

n/a

##### 6.2.2 Test Cycle Exit Criteria

n/a

##### 6.2.3 Test Cycle Abnormal Termination

n/a


## 7. Deliverables

## 7.1 Test Evaluation Summaries

n/a

## 7.2 Reporting on Test Coverage

Jacoco provides an report on test coverage every GitHub Pull Request, listing the test coverage for every package and class of the non-testing code.

## 7.3 Perceived Quality Reports

n/a

## 7.4 Incident Logs and Change Requests

Jacoco is used to generate a report on test coverage. It output the file in HTML-format.

## 7.5 Smoke Test Suite and Supporting Test Scripts

n/a

## 7.6      Additional Work Products
n/a

### 7.6.1     Detailed Test Results
n/a

### 7.6.2     Additional Automated Functional Test Scripts
-

### 7.6.3     Test Guidelines
n/a

### 7.6.4     Traceability Matrices
n/a


## 8. Testing Workflow

The implementation of new feature or functionality is paired with development of test for said features and functionality. The developer has to decide with type of tests are most fitting for the new code. When all tests pass and an acceptable amount of code coverage is reached the code is pushed into the development branch. 

## 9. Environmental Needs

### 9.1 Base System Hardware

The following table sets forth the system resources for the test effort presented in this Test Plan.

| Resource           | Quantity | Name and Type                               |
|--------------------|----------|---------------------------------------------|
| Local test machine | 3        | Own notebook / PC                           |
| Production Server  | 1        | API provider / Frontend provider / Database |
| GitHub CI/CD       | 1        | Testing, building and deploying application |

### 9.2 Base Software Elements in the Test Environment

The following base software elements are required in the test environment for this Test Plan.

| Software Element Name |  Type and Other Notes                        |
|-----------------------|----------------------------------------------|
| Android Studio        | Test Runner / IDE                            |
| IntelliJ              | Test Runner / IDE                            |
| JUnit 4               | Unit testing library                         |
| Espresso              | UI testing library                           |
| Cucumber              | human readable test definitions              |

### 9.3 Productivity and Support Tools

The following tools will be employed to support the test process for this Test Plan.

| Tool Category or Type | Tool Brand Name                                       |
|-----------------------|-------------------------------------------------------|
| Repository            | [GitHub](https://github.com/)                         |
| CI/CD Service         | [GitHub actions](https://github.com/features/actions) |
| Metrics               | [Jacoco](https://www.jacoco.org/jacoco/trunk/doc/)    |
| Metrics               | [Sonarqube](https://www.sonarqube.org/)               |

### 9.4 Test Environment Configurations

The following Test Environment Configurations need to be provided and supported for this project.

n/a

## 10. Responsibilities, Staffing, and Training Needs

### 10.1 People and Roles

This table shows the staffing assumptions for the test effort.

Human Resources

| Role                                     | Specific Responsibilities or Comments                                          |
|------------------------------------------|--------------------------------------------------------------------------------|
| Test Manager                             | Provides management oversight                                                  |
| Test Designer                            | Defines the technical approach to the implementation of the test effort        |
| Tester                                   | Implements and executes the tests                                              |
| Test System Administrator                | Ensures test environment and assets are managed and maintained                 | 
| Database Administrator, Database Manager | Ensures test data (database) environment and assets are managed and maintained |
| Implementer                              | Implements and unit tests the test classes and test packages                   |

### 10.2 Staffing and Training Needs

n/a

## 11. Iteration Milestones

We want to keep over 20% code coverage.

## 12. Risks, Dependencies, Assumptions, and Constraints

| Risk                                                                     | Mitigation Strategy                 | Contingency (Risk is realized) |
|--------------------------------------------------------------------------|-------------------------------------|--------------------------------|
| [See Risk Management](https://vaultionizer.com/2021/04/11/week-12-hold/) | Continuous Risk Management            | Version Control                |

## 13. Management Process and Procedures

n/a
