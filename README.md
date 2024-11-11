# Project Details

![alt text](image.png)

CICD Pipeline Process

Jira ticket is created by client using either Jira or Service now which would be them requesting a new feature 
![image](https://github.com/user-attachments/assets/23c10e2c-d6db-4dae-acf0-79313c3fb699)

Developer takes the ticket and write the source code for the new feature for the application in their local repository and this will get tested locally and will check if everything is working fine.

Once Confirmed this code will be pushed onto GitHub where the code will be placed in a separate branch to the main branch, then once everything is tested a pull request would be made to merge the changes from feature branch to main branch 

Automatically as soon as new code is pushed to main branch GitHub automatically a GitHub Actions pipeline would be triggered based on commit actions

Compile testing would occur which would checks the source code if there are any syntax errors via the use of maven

Then unit testing could occur to see if the applications run smoothly and passes all the unit tests via the use of maven also  
We’ll then run the code quality check via the use of sonarqube

We’ll then use aqua trivy vulnerability scan to scan our whole repository to ensure we don’t have any bugs or vulnerability within our source code

Now we’re going to build and package the applications which will generate the artefact and the executable file 

Once we build and package the artifact we can then upload it In GitHub


Once the artifact is published within GitHub we’ll now need to build the docker image

After the docker image has being build we’ll now need to scan the docker image to see if its having vulnerabilities or not we’ll be using aqua trivy image scan for this 

Once this is done The image would then be pushed onto a Docker Hub repository 

After this we’ll now be creating our yaml manifest files which would be used to deploy this application onto the Dev Cluster initially 

Then after check everything runs smoothly on the Dev Cluster We’ll now deploy this application to our Amazon EKS cluster 

Once the application is deployed we’ll be monitoring it via the use of Prometheus and Grafana 



# BoardgameListingWebApp Details

## Description

**Board Game Database Full-Stack Web Application.**
This web application displays lists of board games and their reviews. While anyone can view the board game lists and reviews, they are required to log in to add/ edit the board games and their reviews. The 'users' have the authority to add board games to the list and add reviews, and the 'managers' have the authority to edit/ delete the reviews on top of the authorities of users.  

## Technologies

- Java
- Spring Boot
- Amazon Web Services(AWS) EC2
- Thymeleaf
- Thymeleaf Fragments
- HTML5
- CSS
- JavaScript
- Spring MVC
- JDBC
- H2 Database Engine (In-memory)
- JUnit test framework
- Spring Security
- Twitter Bootstrap
- Maven

## Features

- Full-Stack Application
- UI components created with Thymeleaf and styled with Twitter Bootstrap
- Authentication and authorization using Spring Security
  - Authentication by allowing the users to authenticate with a username and password
  - Authorization by granting different permissions based on the roles (non-members, users, and managers)
- Different roles (non-members, users, and managers) with varying levels of permissions
  - Non-members only can see the boardgame lists and reviews
  - Users can add board games and write reviews
  - Managers can edit and delete the reviews
- Deployed the application on AWS EC2
- JUnit test framework for unit testing
- Spring MVC best practices to segregate views, controllers, and database packages
- JDBC for database connectivity and interaction
- CRUD (Create, Read, Update, Delete) operations for managing data in the database
- Schema.sql file to customize the schema and input initial data
- Thymeleaf Fragments to reduce redundancy of repeating HTML elements (head, footer, navigation)

## How to Run

1. Clone the repository
2. Open the project in your IDE of choice
3. Run the application
4. To use initial user data, use the following credentials.
  - username: bugs    |     password: bunny (user role)
  - username: daffy   |     password: duck  (manager role)
5. You can also sign-up as a new user and customize your role to play with the application! 😊
