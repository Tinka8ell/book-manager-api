# 📖 Minimalist Book Manager API

## Introduction
This is the starter repository for the Further APIs session. It provides a start to creating a Minimalist Book Manager API
using a Test-Driven Development approach.

### Pre-Requisites
- Java SE Development Kit 11
- Maven

### Technologies & Dependencies
- Spring Boot
- Spring Web
- H2 Database
- Lombok
- Spring Data JPA

### How to Get Started
- Fork this repo to your Github and then clone the forked version of this repo

### Main Entry Point
- The Main Entry Point for the application is: [BookmanagerApplication.java](src/main/java/com/techreturners/bookmanager/BookmanagerApplication.java)

### Running the Unit Tests
- You can run the unit tests in IntelliJ, or you can go to your terminal and inside the root of this directory, run:

`mvn test`

### Tasks

Here are some tasks for you to work on:

📘 Discussion Task

Explore the code and make notes on the following features and how it is being implemented in the code. 
We'd like you to note down what classes and methods are used and how the objects interact.

The features are:
- Get All Books
  - GET request with no parameter
- Get a Book by ID
  - GET request with book id as parameter
- Add a Book
  - POST request with book as body
- Update a Book
  - PUT request with book id as parameter and with book as body

Seriously do not like the "hidden" nature of so much of this.  I missed the "endpoint" definition the first
time through as it was stuck up behind the class definition.  Only went looking for it when I saw the endpoint being 
used in the test code and tried to work out why it was there.  Can only guess that the annotations are doing behind the 
scenes in the Book Model class!  And there does not seem to be much of an actual repository as the Tests mock it anyway. 

All the above "enter" in the "BookManagerController" as either GET, POST or PUT requests 
with endpoint as "/api/v1/book" and an optional bookID parameter,
and optional Book body.

These are then processed by the "BookManagerServiceImpl" to access some back end repository and either update and / or
return data from that repository. 

The BookManagerController then packages the result as "ResponseEntity" to be returned to the user.  
I can be assumed that this is a JSON body (representing the Book object), a status code and optional headers. 

📘 Task 1: Implement the following User Story with tests.

`User Story: As a user, I want to use the Book Manager API to delete a book using its ID`


📘 Extension Task: Oh no! 😭 We've only covered the happy paths in the solution, can you figure out a way
to add in exception handling to the project? 

- Clue 1: What if someone wants to add a book with an ID for a book that already exists? How do we handle this gracefully?


- Clue 2: What if someone wants to find a book by an ID that doesn't yet exist? 
  How can we improve the API by handling errors gracefully and show a helpful message to the client?
  