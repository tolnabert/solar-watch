<a id="readme-top"></a>

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![LinkedIn][linkedin-shield]][linkedin-url]



Welcome to the Solar Watch project! This repository is divided into two main parts: the backend and the frontend. You can access each part by clicking on the badges below the logo.



<br />
<div align="center">
  <h3 align="center">Solar Watch</h3>
  <a href="https://github.com/tolnabert/solar-watch">
    <img src="images/logo.jpg" alt="Logo" width="100" height="100">
  </a>
    <a href="https://github.com/tolnabert/solar-watch-backend">
      <img src="https://img.shields.io/badge/Backend_repository-%23007396?style=for-the-badge&logo=spring&logoColor=white" alt="Backend">
    </a>
    <a href="https://github.com/tolnabert/solar-watch-frontend">
      <img src="https://img.shields.io/badge/Frontend_repository-%23F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="Frontend">
    </a>
  </p>
</div>



<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li><a href="#prerequisites">Prerequisites</a></li>
    <li>
      <a href="#project-setup">Project Setup</a>
      <ul>
        <li><a href="#manual-setup">Manual Setup</a></li>
          <ul>
            <li><a href="#backend">Backend</a></li>
            <li><a href="#frontend">Frontend</a></li>
          </ul>
        <li><a href="#docker-setup">Docker Setup</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
  </ol>
</details>



## About The Project

Solar Watch is a web application designed to provide sunrise and sunset information for various cities. This project encompasses a backend developed with Java Spring Boot 3 and a frontend built with React and JavaScript.ű
During the development I used Trello to track my ideas and plan my sprints:

- [Trello for the project](https://trello.com/b/GluZg8SJ/solar-watch-si-project)

This project was completed as part of the final module of my course, during the self-directed weeks. It offers users the ability to register, login, and obtain solar timings for any city by integrating with two external APIs:

- [OpenWeatherMap Geocoding API](https://openweathermap.org/api/geocoding-api)
- [Sunrise-Sunset API](https://sunrise-sunset.org/api)

By leveraging these APIs, Solar Watch delivers comprehensive solar information for specified locations. The application also includes secure endpoints reserved for admin users. Admins have the capability to add solar data not provided by external sources and review all stored solar information requests in the my database.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



### Built With

This section is listing  major frameworks/libraries use in my project.

* [![Node][Node.js]][Node-url]
* [![Javascript][Javascript.com]][Javascript-url]
* [![React][Reactjs.org]][Reactjs-url]
* [![PostgreSQL][Postgresql.org]][Postgresql-url]
* [![Java][Java.com]][Java-url]
* [![Spring][Spring.io]][SpringBoot-url]
* [![SpringSec][SpringSec]][SpringSec-url]
* [![Hibernate][Hibernate]][Hibernate-url]
* [![Express][Express.com]][Express-url]
* [![Docker][Docker.com]][Docker-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>



### Prerequisites

Before setting up the project, ensure you have the following programs installed based on your pereference that you choose:

#### Manually Setup

- **Java Development Kit (JDK)**: Required for running the backend.
  - Install JDK from: [Oracle JDK download page](https://www.oracle.com/java/technologies/downloads/)

- **Maven**: Required for building and running the backend.
  - Install Maven from: [Apache Maven download page](https://maven.apache.org/download.cgi)

- **Node.js**: Required for running the frontend.
  - Install Node.js from: [Node.js download page](https://nodejs.org/en/download/package-manager)

#### Docker Setup

- **Docker**  
   - Install Docker from: [Docker Desktop download page](https://www.docker.com/products/docker-desktop).

- **Docker Compose**  
   - Docker Compose is included with Docker Desktop, but you can also install it separately for Linux from: [Docker Compose download page](https://docs.docker.com/compose/install/).

<p align="right">(<a href="#readme-top">back to top</a>)</p>



### Project Setup

You need to configure environment variables, for that I noted the necessary ones see below:

- DB_NAME: The name of the PostgreSQL database.
  
    ```
    DB_NAME=solarwatch
    ```

- DB_USERNAME: The PostgreSQL username.
  
    ```
    DB_USERNAME=postgres
    ```

- DB_PASSWORD: The PostgreSQL password.

    ```
    DB_PASSWORD=postgres
    ```
 
- DB_URL: The JDBC URL for connecting to the PostgreSQL database.

  ```
  DB_URL=jdbc:postgresql://localhost:5432/solarwatch
  ```
  
- JWT_SECRET: A secret key used for signing JWTs. Replace your_jwt_secret_here with a secure value.

  ```
  JWT_SECRET=your_jwt_secret_here
  ```
  
If you need you can run the following node.js script to generate a random string and copy it:

  ```
  node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
  ```

Replace paste-the-generated-string-here with the string you copied.

  ```
  JWT_SECRET = paste-the-generated-string-here
  ```

#### Manual Setup

Clone the Repository

  First, clone the main repository that contains both the backend and frontend:
  
  ```
  git clone https://github.com/tolnabert/solar-watch
  ```

##### Backend

1. Navigate to the Backend Directory

  Change into the backend directory from the root:

  ```
  cd backend
  ```

2. Build and Run the Backend

  Ensure you have JDK and Maven installed. Run the following command to build and start the backend service:

  ```
  mvn spring-boot:run
  ```

3. Verify Backend Installation

  Access the backend service at http://localhost:8080/api/test/public.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



##### Frontend

1. Navigate to the Frontend Directory
  
  ```
  cd frontend/react
  ```

2. Install Dependencies

  ```
  npm install
  ```

3. Build and Run the Frontend

  ```
  npm run dev
  ```

4. Verify Frontend Installation

  Access the frontend service at http://localhost:5173.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


#### Docker Setup

To set up the project using Docker, follow these steps:

1. Clone the repository to your local machine:

  ```
  https://github.com/tolnabert/solar-watch
  ```

2. Navigate to the Root of the Repository

  ```
  cd your-repo
  ```

3. Start the application with Docker Compose

  Run the following command to start all services defined in the docker-compose.yml file:

  ```
  docker-compose up -D
  ```

4. Access the Application

  Application: http://localhost:5008

<p align="right">(<a href="#readme-top">back to top</a>)</p>



### Usage

If you can access the http://localhost:5173, you can use the features:

- login
    - You may login as admin to access all features:
      ```
      username: admin
      password: secret123
      ```
      
    - or login with test user:
      ```
      username: testuser
      password: secret123
      ```
- register

As a user:
- search with a city name for solar information
    - country code country code divided by comma. Please use ISO 3166 country codes
    - state code (only for the US country)
- visit about us, contact, change password pages (not finished, not in scope to finish in this project)

As an admin:
- you can add solar information to be able to manage solar information that are not included for the external APIs.
- you can list all solar information that is in our database
    - a request that is not in our database will be saved to it, form next time the server will serve that.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



## Roadmap

### Core Features

- [x] **User Registration**
- [x] **User Login**
- [x] **Security**
    - [x] **Admin Role: Full Access**
      - [x] List All Solar Information
      - [x] Manually Add Solar Information
      - [ ] Delete Solar Information
    - [x] **User Role: Access to Personal Data and Search Features**
      - [x] Search Solar Information
      - [x] Access to Change Password 
    - [x] **Guest Role: Limited Access to Public Pages**
- [x] **CSS Styling**
- [x] **Display Search Results in Chronological Order**
- [x] **Multi-Layer Dockerization**
- [x] **Continuous Integration (CI)**
  - [x] Integrate Docker Hub Image Update
- [x] **Integration Testing**
- [x] **Unit Testing**

<p align="right">(<a href="#readme-top">back to top</a>)</p>



<!-- MARKDOWN LINKS & IMAGES -->
<!-- BANNER -->
[contributors-shield]: https://img.shields.io/badge/CONTRIBUTORS_-1-green?style=for-the-badge
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/badge/FORKS_-0-blue?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/badge/STARS-0-blue?style=for-the-badge
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/badge/ISSUES-0-yellow?style=for-the-badge
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[linkedin-shield]: https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white
[linkedin-url]: https://www.linkedin.com/in/tolnabert

<!-- LINKS TO BACKEND AND FRONTEND -->
[Backend]: https://img.shields.io/badge/Backend_repository-%23007396?style=for-the-badge
[Backend-url]: https://github.com/tolnabert/solar-watch-backend  
[Frontend]: https://img.shields.io/badge/Frontend_repository-%23F7DF1E?style=for-the-badge
[Frontend-url]: https://github.com/tolnabert/solar-watch-frontend

<!-- TECHNOLOGIES -->
[Node.js]: https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white
[Node-url]: https://nodejs.org/en
[Javascript.com]: https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white
[Javascript-url]: https://www.javascript.com/
[Reactjs.org]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[Reactjs-url]: https://reactjs.org/
[Postgresql.org]: https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white
[Postgresql-url]: https://www.postgresql.org/
[Java.com]: https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white
[Java-url]: https://www.java.com/en/
[Spring.io]: https://img.shields.io/badge/spring-%236DB33F.svg?style=for-the-badge&logo=spring&logoColor=white
[SpringBoot-url]: https://spring.io/projects/spring-boot
[SpringSec]: https://img.shields.io/badge/Spring_Security-6DB33F?style=for-the-badge&logo=Spring-Security&logoColor=white
[SpringSec-url]: https://spring.io/projects/spring-security
[Hibernate]: https://img.shields.io/badge/Hibernate-59666C?style=for-the-badge&logo=Hibernate&logoColor=white
[Hibernate-url]: https://docs.spring.io/spring-framework/reference/data-access/orm/hibernate.html
[Express.com]: https://img.shields.io/badge/express.js-%23404d59.svg?style=for-the-badge&logo=express&logoColor=%2361DAFB
[Express-url]: https://expressjs.com/
[Docker.com]: https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white
[Docker-url]: https://www.docker.com/
