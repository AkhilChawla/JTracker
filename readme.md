# J-Tracker - Your Job Tracking Assistant

[![GitHub license](https://img.shields.io/github/license/jashgopani/application-tracking-system)](https://github.com/jashgopani/application-tracking-system/blob/main/LICENSE)
[![DOI](https://zenodo.org/badge/426259091.svg)](https://zenodo.org/badge/latestdoi/426259091)
[![codecov](https://codecov.io/gh/SoftwareEngineering-HomeWork/application-tracking-system/branch/main/graph/badge.svg)](https://codecov.io/gh/SoftwareEngineering-HomeWork/application-tracking-system)
[![GitHub issues](https://img.shields.io/github/issues/SoftwareEngineering-HomeWork/application-tracking-system)](https://github.com/jashgopani/application-tracking-system/issues)
[![Github closes issues](https://img.shields.io/github/issues-closed-raw/SoftwareEngineering-HomeWork/application-tracking-system)](https://github.com/jashgopani/application-tracking-system/issues?q=is%3Aissue+is%3Aclosed)
![GitHub top language](https://img.shields.io/github/languages/top/SoftwareEngineering-HomeWork/application-tracking-system)

<p align="center"><img width="700" src="./resources/ApplicationTrackingAnimation.gif"></p>

The process of applying for jobs and internships is not a cakewalk. Managing job applications is a time-consuming process. Due to the referrals and deadlines, the entire procedure can be stressful. Our application allows you to track and manage your job application process, as well as regulate it, without the use of cumbersome Excel spreadsheets.

Our application keeps track of the jobs you've added to your wish list. It also keeps track of the companies you've already applied to and keeps a list of any rejections. Rather than having the user browse each company's site for potential prospects, our application allows the applicant to search for them directly using basic keywords. Any prospective work offers can then be added to the applicant's wishlist.


## New Features in Phase 4
🎥[Phase-4 Demo Video](https://youtu.be/VKTob1N19ug)

## ⭐ Highlight of Phase 4 ⭐
In Phase 4 of this project, we undertook a significant overhaul of both the backend and frontend to enhance maintainability, scalability, and performance. This document outlines the key improvements, new features, and technical changes made during this phase.

Phase 4 Highlights
1. Backend Transformation: From Flask/Django to Node.js
The previous backend was implemented in a mix of Flask/Django frameworks, resulting in complexity and code duplication across multiple modules. We have now transitioned the entire backend to Node.js. Below are the key benefits of this migration:

Benefits of Moving to Node.js
Unified Language: Both the frontend (React/JavaScript) and backend now use JavaScript, streamlining development and allowing for code reuse.
Asynchronous Non-blocking I/O: Node.js supports asynchronous programming, improving performance by handling multiple requests concurrently.
Scalability: Node’s event-driven architecture makes it more suitable for microservices, allowing the application to scale efficiently.
Extensive Package Ecosystem: Leveraged npm (Node Package Manager) for faster development with access to numerous libraries and modules.
Reduced Overhead: Node.js eliminates the need for heavyweight frameworks like Django, offering a leaner setup that is easier to maintain.
Revised Backend Architecture: MVC Microservices
The original backend consisted of over 800 lines of tightly coupled code, making it difficult to debug and extend. The codebase has now been modularized into Model-View-Controller (MVC) microservices architecture.

Separation of Concerns: Each component (Models, Controllers, Views) has a distinct role, promoting clean code and maintainability.
Independent Microservices: Business logic is divided into modular microservices (e.g., User Service, Job Service, Recruiter Service) that communicate via APIs, allowing for easier debugging and future expansion.
API Gateway: Centralized routing for all microservices, improving security and simplifying external communication.
This refactoring also improved the backend-frontend integration. We updated outdated package dependencies across both layers to eliminate compatibility issues that previously caused communication failures between the two.

2. New Feature: Recruiter Dashboard
A key addition in Phase 4 is the Recruiter Dashboard. This feature allows recruiters to filter and fetch candidate profiles that match job descriptions using advanced search parameters.

Technical Details
Search Functionality:
Uses MongoDB Aggregation Pipelines to perform complex searches on candidate profiles (e.g., filtering by skills, experience, location).
Implements full-text search and fuzzy matching to handle spelling variations and synonyms.
Authentication and Authorization:
Secure access through JWT-based authentication.
Role-based authorization ensures that only users with recruiter privileges can access this feature.
Data Caching:
Frequently accessed data is cached using Redis, reducing database load and improving response times.
UI/UX: Built using React.js with intuitive filters and quick profile previews for a seamless recruiter experience.
3. Chrome Extension: Smart Application Helper
We also developed a Chrome Extension to assist users in filling out job applications efficiently. This extension saves users' job-related information and autofills applications to reduce repetitive tasks.

How the Chrome Extension Works
Content Script:

Injects JavaScript into the web pages of job application portals.
Monitors form fields on the page and detects matching input fields (e.g., name, email, work experience).
Uses stored user data to autofill these fields when possible.
Service Worker:

Runs in the background and handles communication between the extension popup, content scripts, and backend.
Manages events like receiving updates from the backend (e.g., new job matches) and relays them to the extension.
Handles API calls to sync data between the browser and the backend.
Storage:

User information is saved locally using Chrome's storage API (with encryption) to ensure security.
Provides a convenient UI for users to edit and manage their stored data via the extension popup.
This extension improves the user experience by streamlining job applications and reducing manual effort, making it a practical companion for active job seekers.

4. Web Scraping for Daily Job Recommendations
To keep users informed about the latest job openings, we implemented a web scraping module that provides daily job recommendations.

Technical Details
Scraping Strategy:

Uses Puppeteer (a Node.js library) to automate job search on various job boards and scrape job listings.
Extracts relevant job information (title, company, location, description) and stores it in the backend.
Frequency and Caching:

The scraping runs on a scheduled cron job to fetch new listings daily.
To prevent scraping the same listings multiple times, previously fetched jobs are cached and tracked in the database.
Recommendation Logic:

User preferences (e.g., location, job type, skills) are matched against the scraped job listings.
Personalized job recommendations are delivered via email notifications or displayed on the dashboard.
Summary
In Phase 4, we successfully transformed the job tracker application into a more maintainable, scalable, and feature-rich platform. The migration to Node.js, restructuring of the backend into a microservices-based MVC architecture, and the addition of new functionalities such as the Recruiter Dashboard and Chrome Extension have significantly enhanced both developer and user experiences. Our daily job recommendations feature ensures users are always up to date with the latest opportunities.

These improvements lay the foundation for future growth, making the platform well-suited for continuous enhancement and scaling as new requirements arise.

---

### Application Demo video

https://user-images.githubusercontent.com/89501363/144725439-5d9191f8-df13-4814-aa15-99cd752ab0cc.mp4

## Table of contents

- [Basic Design](#basic-design)
- [Samples](#samples)
- [New Features In Phase 3](#new-features-in-phase-3)
- [Future Scope](#future-scope)
- [Explanation](#explanation)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
  - [Requirements](#requirements)
  - [Steps to follow for the installation](#steps-to-follow-for-the-installation)
- [Hosting the Database](#hosting-the-database)
  - [Local MongoDB](#local-mongodb)
  - [Hosted database with MongoDB Atlas](#hosted-database-with-mongodb-atlas)
- [License](#license)
- [How to Contribute](#how-to-contribute)
- [Team Members](#team-members)

## Basic Design:

![Basic Design](https://github.com/prithvish-doshi-17/application-tracking-system/blob/main/resources/Overall%20Design.PNG)

## Samples:

### Login Page / Signup Page

The introductory visual interface displayed from which a user is able to register and log into the application. User can also login or sign up through Google Authorization.

<p align="center"><img width="700" src="./resources/login_page.png"></p>
The Google Authorization Login:

<p align="center"><img width="700" src="./resources/googleauth.png"></p>

### HomeScreen - Profile Page

After Logging In, the Profile page of the user is displayed where the user details such as Name, Institution, email, phone number, address, skills, and more are shown.
Users can add or update information to their profile, such as their personal information, skills, preferred job locations, and their experience level.

<p align="center"><img width="700" src="./resources/profilepage.png"></p>

### SearchPage

The interface through which a user is able to search for specific jobs and apply on them through the 'Apply' button.

1. Navigate to Job search page, search for particular Job.
2. Click on Details button to see the Job Details
3. Click on Apply button which will redirect to the Job Apply link.

<p align="center"><img width="700" src="./resources/search_roles_companywise.png"></p> 
<p align="center"><img width="700" src="./resources/FindJobs.png"></p>
<p align="center"><img width="700" src="./resources/Job_Description.png"></p>

### ApplicationPage

The user is able to access different saved applications - Waitlisted applications, Waiting for Refereals, Applied Jobs, Application Status. The user can also add more jobs to track through this screen.

<p align="center"><img width="700" src="./resources/AddApplicationpage.png"></p>

### MatchesPage

On this page, user can see different jobs that would be recommended to them based on their profile and their preferences. User can apply for that position from this page too.

<p align="center"><img width="700" src="./resources/Recommendjobspage.png"></p>

## Future Scope:

- Include deadline reminders for the application and interview.
- Add a feature that allows users to attach these reminders to their Google calendar.
- Incorporate notifications for upcoming deadlines.
- Include a link to the university’s career fair page.
- Direct connection to Linkedin, allowing for the addition of job opportunities to the wishlist.
- An option to maintain separate profiles for job tracking.
- Integrate the database into docker

## Explanation:

Currently, we have four fundamental steps in our project:

1. The SearchPage where users can search about the Job Postings
2. The MatchesPage where users get recommendation about the jobs according to their preferences
3. The ApplicationsPage where users can add and see the position they applied to and can update/delete the the information. Any details in any table can be modified at any time during the process
4. The ProfilePage where user can add his skills, experience level and preffered location. This information is used to recommend user jobs that require similar skillsets

## Technologies Used:

- Python
- Node.Js
- Flask
- MongoDB
- React
- Docker

## Installation:

### Requirements:

- [Python](https://www.python.org/downloads/) (recommended >= 3.8)
- [pip](https://pip.pypa.io/en/stable/installation/) (Latest version 21.3 used as of 11/3)
- [npm](https://nodejs.org/en/) (Latest version 6.14.4 used as of 11/3)
- [Docker-Desktop](https://www.docker.com/products/docker-desktop/) (Latest version as of 11/27)

### Steps to follow for the installation:

1. **Clone the Repository**
    - Use the command `git clone https://github.com/jashgopani/application-tracking-system.git` to clone the repository.

2. **Start the Docker Engine**
    - Ensure that Docker is installed on your system. If not, you can download it from the official Docker website.
    - Start the Docker engine on your machine. The command varies based on your operating system.

3. **Build Images**
    - Navigate to the backend folder and build the image for the API using the following command:
        ```
        docker build -f dockerfile.api -t ats-api .
        ```
    - Similarly, navigate to the frontend folder and build the image for the client using the following command:
        ```
        docker build -f dockerfile.client -t ats-client .
        ```

4. **Run Docker Compose**
    - Finally, run the following command to start the application:
        ```
        docker-compose up
        ```

## Hosting the Database:

### Local MongoDB:

1. Download [MongoDB Community Server](https://docs.mongodb.com/manual/administration/install-community/)
2. Follow the [Installion Guide](https://docs.mongodb.com/guides/server/install/)
3. In app.py set 'host' string to 'localhost'
4. Run the local database:

mongodb

- Recommended: Use a GUI such as [Studio 3T](https://studio3t.com/download/) to more easily interact with the database

### Hosted database with MongoDB Atlas:

1. [Create account](https://account.mongodb.com/account/register) for MongoDB

- **If current MongoDB Atlas owner adds your username/password to the cluster, skip to step 4** \*

2. Follow MongoDB Atlas [Setup Guide](https://docs.atlas.mongodb.com/getting-started/) to create a database collection for hosting applications
3. Create application.yml in the backend folder with the following content:
   ```
   GOOGLE_CLIENT_ID : <Oauth Google ID>
   GOOGLE_CLIENT_SECRET : <Oauth Google Secret>
   CONF_URL : https://accounts.google.com/.well-known/openid-configuration
   SECRET_KEY : <Any Secret You Want>
   USERNAME : <MongoDB Atlas Username>
   PASSWORD : <MongoDB Atlas Password>
   CLUSTER_URL : <MongoDB Cluster URL>
   ```
4. In app.py set 'host' string to your MongoDB Atlas connection string. Replace the username and password with {username} and {password} respectively
6. For testing through CI to function as expected, repository secrets will need to be added through the settings. Create individual secrets with the following keys/values:

MONGO_USER: <MongoDB Atlas cluster username>
MONGO_PASS: <MongoDB Atlas cluster password>

## License

The project is licensed under the [MIT](https://choosealicense.com/licenses/mit/) license.

## How to Contribute?

Please see our CONTRIBUTING.md for instructions on how to contribute to the repository and assist us in improving the project.

## Team Members

- Akhilesh Neeruganti
- Jash Gopani
- Hemil Mehta
- Rohan Ajmera

## Contact Info
For any questions, please email neerua08@gmail.com.
