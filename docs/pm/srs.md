---
layout: default
title: SRS
nav_order: 1
parent: Project management
---
# Software Requirements Specification 
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## 1. Introduction

### 1.1 Purpose
This Software Requirements Specification (SRS) describes all specifications for the application "Vaultionizer". It includes an overview about this project and its vision, detailed information about the planned features and boundary conditions of the development process.


### 1.2 Scope
The project is going to be realized as an Android App and a Spring Back-End application for the file storage and user-management itself.
For the scope of this project we decided to realise the proejct as an Android App only, because most users out there have a smartphone that runs this operating system.

Planned Subsystems are: 
* User system
  * 
* 

### 1.3 Definitions, Acronyms and Abbreviations

| Abbrevation | Explanation                            |
|:-----------:|:--------------------------------------:|
| SRS         | Software Requirements Specification    |
| UC          | Use Case                               |
| n/a         | not applicable                         |
| tbd         | to be determined                       |
| UCD         | overall Use Case Diagram               |
| FAQ         | Frequently asked Questions             |

### 1.4 References

| Title                                       | Date       | Publishing organization   |
| ------------------------------------------- |:----------:| ------------------------- |
| [Website &  Blog](https://vaultionizer.com) | 18.10.2020 | Common Playground Team    |
| [GitHub](https://github.com/vaultionizer/)  | 18.10.2020 | Vaultionizer              |


### 1.5 Overview
The following chapter provides an overview of this project with vision and Overall Use Case Diagram. The third chapter (Requirements Specification) delivers more details about the specific requirements in terms of functionality, usability and design parameters. Finally there is a chapter with supporting information. 
    
## 2. Overall Description

### 2.1 Vision
Vaultionizer is a highly dynamic and secure app which allows you to keep all your personal information and files in one place – far away from any company that wants your juicy data.
The goal is no to be the next Dropbox or Google Drive, the approach here is a little bit different and requires some own effort from the user.
Instead of trusting a third party service, the user alone will be able to decide where his data is stored by using the back-end we provide. 
Together with our multi-purpose app Vaultionizer will provide the user with the tools necessary to store his data in a secure manner.
We will only provide a demo back-end for all users that want to try our app, but in order to unlock all features they have to host the back-end themselves.

### 2.2 Use Case Diagram

![OUCD](./../../img/UCV.svg)

- Green: Planned till end of december
- White: Planned till end of june (next semester)

### 2.3 Technology Stack
The technology we use is:

Backend:
* Maven, Spring Boot and other libraries ([Details](https://github.com/vaultionizer/vault-server/blob/master/pom.xml))

Frontend:
* Android, Java, Maven

IDE:
* IntelliJ
* Android Studio

Project Management:
* YouTrack
* GitHub
* Discord
* Telegram

Deployment:
* GitHub Actions
* Docker

Testing:
* Cucumber
* JUnit
* Codacy

## 3. Specific Requirements

### 3.1 Functionality
This section will explain the different use cases, you could see in the Use Case Diagram, and their functionality.  

#### 3.1.1 Upload file
The user can upload files to his personal secure space. All of these files are encrypted via a personal key.

#### 3.1.2 Upload personal container
The app will not only support the storage of files. You can also store all of your personal information like social security numbers, contact and more. The Android app will provide a seperate UI for this.
Of course these information will get encrypted too.

#### 3.1.4 View file structure
The user can view the file structure without downloading any files.

#### 3.1.5 Download file
The user can download individual files. They get decrypted locally in order to provide strong security.

#### 3.1.6 Download personal container
As mentioned in section 3.1.2 we offer the possibility to create a container for personal data.
This container can be synced between multiple devices.

#### 3.1.9 Register
The app offers the ability to create an account on the server. This registration process is, however, restricted. The admin of the back-end is required to generate an authentification key that the user must provide for the registration. Besides this key, the user must also provide a host, an username and a secure master password.

#### 3.1.8 Login
First of all the user must provide a host on which our back-end is running. The login itself is done via the username and master password.

#### 3.1.10 Regenerate keys
It is possible to invalidate an encrpytion key and generate a new one. All files that were previously encrypted with that key are now encrypted using the new one and uploaded again. 

#### 3.1.11 Delete keys
Users can delete exisiting keys.

#### 3.1.13 Create space
Users on the same back-end have the possibility to create a shared space. It is pretty similar to a shared folder on Dropbox or Google Drive. The space is, of course, encrypted via a shared key. The owner of the space must exchange this key with other users via a method described in 3.1.15.

#### 3.1.14 Delete Space
Space owners can delete their spaces.

#### 3.1.15 Generate key for invitations
Because spaces have no searchable name and are usally hidden from other users, the space owner must generate an invitation key. This key is used to find the space on the server. Furthermore it is required to exchange the encryption key itself to decrypt the data.

#### 3.1.12 Exchange keys
Users can exchange encryption keys via a QR Code or Bluetooth. This is important for shared spaces because the server is never involved in any kind of key exchange.

### 3.2 Usability
We plan on designing the user interface as intuitive and self-explanatory as possible to make the user feel as comfortable as possible using the app. Though an FAQ document will be available, it should not be necessary to use it. We also provide documentation for more complicated features.
We also want to provide a detailed step by step installation guide for the back-end.

#### 3.2.1 No training time needed
Our goal is that a user installs the android application, opens it and is able to use all features without any explanation or help. This includes external documents like a FAQ or other types of tutorials.

#### 3.2.2 Familiar Feeling
We want to implement an app with familiar designs and functions. This way the user is able to interact in familiar ways with the app without having to get to know new interfaces.

### 3.3 Reliability

#### 3.3.1 Availability
The server shall be available 95% of the time. This also means we have to figure out the "rush hours" of our app because the downtime of the server is only tolerable when as few as possible players want to use the app.

#### 3.3.2 Defect Rate
Our goal is that we have no loss of any data. This is important so that the game sessions can carry on, even after a downtime of the server.

### 3.4 Perfomance

#### 3.4.1 Capacity
The system should be able to manage thousands of requests. For the back-end bandwidth will be pretty important if many users upload or download files simultaneously.

#### 3.4.2 Storage 
Smartphones don't provide much storage. Therefore we are aiming to keep the needed storage as small as possible. Before the files are encrypted and uploaded to the server the app uses a general puropose compression algorithm in order to reduce the file size.

#### 3.4.3 App perfomance / Response time
To provide the best App perfomance we aim to keep the response time as low as possible. This will make the user experience much better.

### 3.5 Supportability

#### 3.5.1 Coding Standards
We are going to write the code by using all of the most common clean code standards. For example we will name our variables and methods by their functionalities. This will keep the code easy to read by everyone and make further developement much easier.
Pull requests and code reviews will ensure that we adhere to these standards.

#### 3.5.2 Testing Strategy
The application will have a high test coverage and all important functionalities and edge cases should be tested. Further mistakes in the implementation will be discovered instantly and it will be easy to locate the error.

### 3.6 Design Constraints
We are trying to provide a modern and easy to handle design for the UI aswell as for the architecture of our application. To achieve that the functionalities will be kept as modular as possible.

Because we are progamming an Android App we chose Java as our programming language. Also we are using the common MVC-architecture to keep the front end and back end seperated. For a clean front end structure we use MVVM.
To make the communication between the two parts easy, we will implement a RESTful-API between them which will provide the data in JSON-Format. 
The supported Platforms will be:
- Android 4.4 and higher
- Java 8 and higher

### 3.7 On-line User Documentation and Help System Requirements
The usage of the app should be as intuitive as possible so it won't need any further documentation. If the user needs some help we will implement a "Help"-Button in the App which includes a FAQ and a formular to contact the developement team.

### 3.8 Purchased Components
We don't have any purchased components yet. If there will be purchased components in the future we will list them here.

### 3.9 Interfaces

#### 3.9.1 User Interfaces
The User interfaces that will be implented are:
- Dashboard - lists all session and makes it possible to filter sessions
- Session Page - shows detailed information about the session and makes it possible to connect session attendants for example via messaging system
- Login - this page is used to log in 
- Register - provides a registration form
- Overwiew of personal sessions - shows all the sessions a user participates in
- Friend List - friends can be added
- Profile - makes it possible to post information about yourself, might provide messaging feature, also shows additional information about users (for example: Language, country, favorite games, etc.)
- Settings - shows the settings

#### 3.9.2 Hardware Interfaces
(n/a)

#### 3.9.3 Software Interfaces
The app will be runnable on Android 4.4 and higher. iOS won't be featured at the moment.

#### 3.9.4 Communication Interfaces
The server and hardware will communicate using the https/websocket protocol. 

### 3.10 Licensing Requirements

### 3.11 Legal, Copyright, and Other Notices
The logo is licensed to the Common Playground Team and is only allowed to use for the application. We do not take responsibilty for any incorrect data or errors in the application.

### 3.12 Applicable Standards
The development will follow the common clean code standards and naming conventions. Also we will create a definition of d which will be added here as soon as its complete.

## 4. Supporting Information
For any further information you can contact the Common Playground Team or check our [Blog](https://vaultionizer.com). 
The Team Members are:
- Johannes Quast
- Julien Meier
- Yannic Hemmer
