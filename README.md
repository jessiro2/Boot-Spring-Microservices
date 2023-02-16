# Sprint-Boot-Microservices Take-aways

Eureka Server is an application that holds the information about all client-service applications.

Every Micro service will register into the Eureka server and Eureka server knows all the client applications running on each port and IP address. Eureka Server is also known as Discovery Server

What is Payload in an API?
  It's the data you are interested in transporting to the server when you make an API request.

Link for the tutorial: https://www.youtube.com/watch?v=35EQXmHKZYs&t=3647s

## Agenda:
- Create a few microservices
- Having them communicate with each other
  
  ![image](https://user-images.githubusercontent.com/122644251/218755015-4366ca95-f971-4ddc-a311-783e8e65e9e1.png)
  
 - Patterns - Make microservices work well together
 - Technologies - Libraries and frameworks to solve common problems
  
  Service-oriented architeture - service for reusability.
  
  
**Movie Catalog API application**

3 microservices

**First micro-service:** Called Movie catalog service - it is responsible for providing the payload. Given a name it'll return an array of movies.
- Input: User ID.
- Output: Movie list with details.

**Second micro-service:** Called Movie Info Service - it is responsible for giving movie information.
- Input: Movie ID.
- Output: Movie details.

**Third micro-service:** Called Rating Data Service - it is where we will be storing what rating a particular user has given for a particular movie.
- Input: User ID.
- Output: Movie IDs and ratings.

Create3 Spring Boot projects
- build movie catalog service API
- Build movie infor service API
- Build ratings data service API
- Have movie catalog service call the other 2 services 

Step 1: Create the 3 services
Question - How to start a spring boot application?
 - Using Maven and adding the required dependencies.
 - Using Spring CLI.
 - Using start.spring.io

 **How to make a REST call from your code?**
   - Calling REST APIs programatically
   - Using a REST client Library
   - Spring Boot cpomes with a client already in your classpath - Rest Template

**How to create a single instance of any object in a Spring application and have it shared across multiple other multiple classes?**
    - Creating a beans - bean by default is a singleton and use dependency injection.
   
 **How to handle security when communicating between microservices?**
   - Using HTTPS
   - Using Authentication
   
 **Why hard coded URLs are bad?**
   - Changeds require code updates
   - Dynamic URLSs in the cloud
   - Load balancing
   - Multiple environments

 **Spring Cloud uses client side discovery**

![image](https://user-images.githubusercontent.com/122644251/219103876-0ad8cd76-468b-480f-a53c-7112301a0f77.png)
 
 
 **Spring handles caching and you can turn it off**.


 **Undestanding Service discovery**
   - Register the microservices in the Discovery server.


Steps to making this work:
  - Start up a Eureka server
  - Have microservices register (publish) using Eureka client
  - Have microservices locate (consume) using Eureka client


