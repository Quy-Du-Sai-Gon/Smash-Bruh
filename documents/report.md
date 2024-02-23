## 1. SmashBruh Movie Renting Website - Documentation

### 1.1. Team member

| Full Name            | Student Id | Tasks                                                                                                                                                                                                                |     |
| -------------------- | :--------: | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
| Nguyễn Ngọc Vĩnh     |   18691    | Movie and TV Shows details, trailers, and recommendations backend API; Movie Search and Filtering API; UI/UX of Homepage and MoviePage; Responsible for Markdown and Swagger Documentation, Analytics and Reporting. |     |
| Hà Quách Phú Thành   |   18840    | Moderate and in charge of frontend and backend; Manage members work and meetings; configure CI/CD, pipeline and Docker development;                                                                                  |
| Thái Quang Nam       |   18770    | Design UI for Navbar, HomePage, FeatureMoviePage, TVShowsPage, MyListPage, SearchPage; Markdown Documentation, Reporting                                                                                             |
| Phạm Hoàng Việt      |   18334    | Design MoviePages and ShowPages ; Markdown Documentation, Reporting User Interface                                                                                                                                   |
| Nguyễn Xuân Khang    |   18973    | Set up Frontend and Backend ProfilePage; Markdown Documentation                                                                                                                                                      |
| Nguyễn Khắc Hoàng    |   18230    | Overall UI, ProfilePage, Login/RegisterPage, AccountPage; Markdown Documentation, Reporting                                                                                                                          |
| Lê Duy               |   17434    | Set up Email Verification, Security; Markdown Documentation; Reporting                                                                                                                                               |
| Trần Ngọc Duy Chương |   17197    | Backend for OAuth2, Authentication; Markdown Documentation; Reporting                                                                                                                                                |
|                      |            |

### 1.2. About our project

Introducing our advanced movie rental application, providing an exceptional cinematic experience. With a user-friendly interface, diverse movie collection, and personalized rental queues, our app offers navigation and immersive film exploration. Discover captivating narratives, acclaimed works, and a wide range of genres on your screen.

With our media rental web application, you can now keep track of rented movies and TV show, as well as keeping track of your favourites and rate them accordingly, provided to you with one of the largest movie database - The Movie Database (TMDB) - a free and open movie database for developers, which also acts as our main API for working with movies/shows.

### 1.3. Table of content

- [1. SmashBruh Movie Renting Website - Documentation](#1-smashbruh-movie-renting-website---documentation)
  - [1.1. Team member](#11-team-member)
  - [1.2. About our project](#12-about-our-project)
  - [1.3. Table of content](#13-table-of-content)
- [2. Introduction](#2-introduction)
  - [2.1. Project Overview](#21-project-overview)
  - [2.2. Objective](#22-objective)
- [3. System Analysis](#3-system-analysis)
  - [3.1. Business Requirements](#31-business-requirements)
  - [3.2. User Requirements](#32-user-requirements)
  - [3.3. Functional Requirements](#33-functional-requirements)
  - [3.4. Non-Functional Requirements](#34-non-functional-requirements)
- [4. System Design](#4-system-design)
  - [4.1. System Diagrams](#41-system-diagrams)
    - [4.1.1. Use Cases](#411-use-cases)
    - [4.1.2. Sequence](#412-sequence)
  - [4.2. System Architecture](#42-system-architecture)
    - [4.2.1. MVC Models for Web Development](#421-mvc-models-for-web-development)
  - [4.3. Components Design](#43-components-design)
    - [4.3.1. Users Interface:](#431-users-interface)
    - [4.3.2. Authentication Interface:](#432-authentication-interface)
    - [4.3.3. Administration Interface:](#433-administration-interface)
  - [4.4. Structure and Relationships](#44-structure-and-relationships)
  - [4.5. Data Model:](#45-data-model)
  - [4.6. GUI](#46-gui)
    - [4.6.1. Login Screen](#461-login-screen)
    - [4.6.2. Homepage](#462-homepage)
    - [4.6.3. Feature Movies](#463-feature-movies)
    - [4.6.4. TV Shows](#464-tv-shows)
    - [4.6.5. My Lists](#465-my-lists)
    - [4.6.6. Profile Page](#466-profile-page)
    - [4.6.7. Movie Page](#467-movie-page)
    - [4.6.8. TV Page Module](#468-tv-page-module)
  - [4.7. Functionality Design](#47-functionality-design)
- [5. Implementation](#5-implementation)
  - [5.1. File Structure](#51-file-structure)
  - [5.2. Development Environment and Technology Stack](#52-development-environment-and-technology-stack)
  - [5.3. CI/CD Testing, Docker and Deployment](#53-cicd-testing-docker-and-deployment)
    - [5.3.1. Test Stage:](#531-test-stage)
    - [5.3.2. Build Stage:](#532-build-stage)
    - [5.3.3. Deploy Stage:](#533-deploy-stage)
  - [5.4. API Utilization](#54-api-utilization)
    - [5.4.1. Movies](#541-movies)
    - [5.4.2. TV Shows](#542-tv-shows)
    - [5.4.3. Discovery](#543-discovery)
- [6. User/Admin Getting Started Guide](#6-useradmin-getting-started-guide)
  - [6.1. User](#61-user)
  - [6.2. Admin](#62-admin)
- [7. Conclusion](#7-conclusion)
  - [7.1. Summary of Project](#71-summary-of-project)
  - [7.2. Future Work](#72-future-work)
  - [7.3. References](#73-references)

## 2. Introduction

### 2.1. Project Overview

SmashBruh is an movie rental web application that aims to simplify the way people discover and rent movies. Our project aims to provide options for users to view the information related to movies and shows. They also have the choice to choose which movies or shows to rent and have their rented information saved for later use. The web app also allows users to perform actions such as liking and rating, which can be viewed, easily accessed and managed.

### 2.2. Objective

- Extensive Movie Library: Curate a diverse collection of films across genres, eras, and cultures to cater to the varied preferences of our users. From classic masterpieces to the latest releases, ensure a wide range of options that cover different cinematic experiences.

- User-Friendly Interface: Develop an intuitive and easy-to-navigate website interface that allows users to explore and discover movies. Implement robust search functionality, filters, and sorting options to facilitate effortless movie browsing.

- Detailed Movie Information: Provide comprehensive and accurate movie information to assist users in making informed decisions. Include detailed descriptions, plot summaries, cast and crew details, user ratings, and reviews to give users valuable insights into each film.

- Personalized Recommendations: Implement a sophisticated recommendation system that analyzes user preferences on the movies and shows currently accessed. Generate personalized movie suggestions that align with users' tastes, helping them discover new films and broaden their cinematic horizons.

- Easy Rental Process: Streamline the movie rental process to make it convenient and hassle-free for users. Implement a straightforward rental system where users can choose their desired movies, rental duration, and complete secure online payments.

## 3. System Analysis

### 3.1. Business Requirements

The business requirements of SmashBruh are as follows:

- Broad Selection of Content: Users expect a wide variety of movies and TV shows across different genres, including popular releases, classics, and niche titles. They want access to a diverse library that caters to their individual preferences and interests.
- User Account Management: SmashBruh requires a user account management system to allow users to create profiles, save preferences, manage their watch lists, and track their searching history. This feature provides a personalized experience and enables users to easily access and organize their preferred content.
- Cross-Platform Accessibility: SmashBruh should be accessible across different devices and platforms, including web browsers, mobile devices, and smart TVs. This ensures that users can enjoy their favorite content conveniently, regardless of the device they are using.
- Analytics and Reporting: The platform requires robust analytics and reporting capabilities to track user behavior, content popularity, and performance metrics. These insights help in making data-driven decisions, improving the user experience, and optimizing the content library.

By fulfilling these business requirements, SmashBruh can create a user-friendly interface, up-to-date information and a stable searching and recommendation system inside the rental movie system to maintain the flow of the website.

### 3.2. User Requirements

The user requirements of SmashBruh are as follows:

- First Time User Experience: SmashBruh provides visitors latest movie that the system have to offer and other information of available movies and shows at the giving moment so that the system keeps up with user's interest.
- Efficient Search and Filtering: Users require an efficient search functionality that allows them to search for specific titles, genres, actors, directors, or keywords. They also expect advanced filtering options to refine their search results based on criteria such as release year, ratings, and language.
- Movie Information Based Recommendations: Users appreciate personalized recommendations based on their current accessed movies and shows. It could be based on names, genres, cast.
- Ratings: Users value the ability to read and contribute to ratings. They want a platform that encourages user feedback, enabling them to make informed decisions and engage in discussions with other movie enthusiasts.
- Flexible Rental Options: Users prefer flexible rental options, including various pricing plans with understandable cost to spend. They want the freedom to choose the rental plan that suits their preferences and viewing habits.
- Cross-Platform Compatibility: Users want the flexibility to access SmashBruh on multiple devices, including web browsers, smartphones, tablets, and smart TVs. They expect a seamless experience that allows them to pick up where they left off across different devices.
- Simple Payment Processing: Users don't have to worry about payment system because we uses simple calculation (addition, subtraction, multiplication and division) based on what users have chosen to be their pricing plan mentioned in the previous part.

By addressing these user requirements, SmashBruh can provide a user-centric experience that meets the expectations of movie enthusiasts, offering them a vast selection of content, seamless navigation and personalized recommendations.

### 3.3. Functional Requirements

The functional requirements of SmashBruh are as follows:

- User Registration and Account Management:
  - Users should be able to create an account and provide necessary information.
  - Users should be able to log in securely and manage their account settings.
- Content Catalog and Search:
  - The platform should maintain a comprehensive catalog of movies and TV shows.
  - Users should be able to search for content by title.
  - Advanced filtering options should be available to refine search results.
- Movie and TV Show Details:
  - Users should be able to view detailed information about each movie or TV show, including synopsis, cast, director, ratings, and reviews.
  - The platform should display relevant recommendations and similar content.
- Rental Options:
  - Users should be able to select rental pricing plans.
  - The platform should provide pricing details, rental durations, and availability information.
- Payment Processing:
  - The platform should securely process payments using simple calculations.
  - Users should receive a decreasing amount of money in their net balance
- My list and Favourites:
  - Users should be able to create and manage a watch list of movies and TV shows.
  - The platform should provide personalized recommendations based on user preferences and ratings.
- Ratings:
  - Users should be able to rate stars score for movies and TV shows.
  - The platform should display average ratings and aggregate reviews for each title.
- Analytics and Reporting:
  - The platform should collect and analyze data to generate insights on user behavior, content popularity, and platform performance.

### 3.4. Non-Functional Requirements

The non-functional requirements of SmashBruh are as follows:

- Performance:
  - The platform should have fast loading times and responsive navigation to provide a seamless user experience.
- Scalability and Availability:
  - The platform should be designed to handle a growing user base and increasing traffic without compromising performance.
  - It should be scalable to accommodate a large number of concurrent users and a growing content library.
  - The platform should have a high level of availability, minimizing downtime and ensuring users can access the service whenever they need it.
  - Measures such as redundancy, load balancing, and backup systems should be in place to maintain availability.
- Security:
  - The platform should implement robust security measures to protect users' personal information, payment details, and viewing history.
  - Secure encryption protocols should be used to ensure the confidentiality and integrity of data.
- Compatibility:
  - The platform should be compatible with various operating systems, web browsers, and devices to accommodate a wide range of user preferences.
  - It should adapt to different screen sizes and resolutions, providing a consistent and optimized experience across devices.
- Usability:
  - The platform should have a user-friendly and intuitive interface, making it easy for users to navigate, search for content, and manage their account.
  - Clear and concise instructions and tooltips should be provided to guide users through different features and functionalities.
- Data Privacy:
  - The platform should comply with data protection regulations and ensure the privacy of user data.
  - Clear privacy policies and consent mechanisms should be in place, informing users about data collection, storage, and usage practices.
- Performance Monitoring and Optimization:
  - The platform should have monitoring mechanisms in place to track performance metrics, identify bottlenecks, and optimize system performance.
  - Regular performance testing and optimization should be conducted to ensure optimal user experience.
- Cross-Platform Accessibility:
  - The platform should be accessible across devices and platforms, including web browsers, mobile devices, and smart TVs.

## 4. System Design

### 4.1. System Diagrams

#### 4.1.1. Use Cases

User Use Case Diagrams

<img  src="UseCases/User/UserUseCaseDiagrams.png" alt="User Use Case" width="1000">

#### 4.1.2. Sequence

- Admin Sequence

<img src="Sequence/AdminSequenceDiagrams.png" alt="AdminSequenceDiagrams" width="1000">

- User Sequence

<img src="Sequence/UserSequenceDiagrams.png" alt="UserSequenceDiagrams" width="1000">

- Database

<img  src="DatabaseDiagram.png" alt="Database" width="1000">

### 4.2. System Architecture

#### 4.2.1. MVC Models for Web Development

The Model-View-Controller (MVC) architecture is a popular design pattern used in the development of software applications. In the context of a movie rental app, the MVC architecture provides a structured and organized approach to manage the different components of the application.

- The Model component of the movie rental app represents the data and the business logic. It encapsulates entities such as movies, users, rentals, and other related data. The Model component includes the data access layer, which interacts with the underlying database or data storage system to perform operations like retrieving, creating, updating, and deleting data. The Model also handles business logic operations, such as validating user inputs, managing rental transactions, integrating with external APIs for fetching movie information, and enforcing data integrity.

- The View component in the movie rental app is responsible for presenting the user interface to the users. It encompasses all the visual elements and user experience components of the application. The View component includes screens, forms, buttons, and other user interface elements that allow users to browse movies, search for movies based on different criteria, view detailed movie information, manage their rental queue, and interact with the application. The View component is designed to be visually appealing, intuitive, and responsive to enhance the overall user experience.

- The Controller component acts as the intermediary between the Model and the View. It receives user input from the View, processes it, and interacts with the Model to fetch or update the data accordingly. The Controller component handles tasks such as processing user requests, managing user authentication and authorization, managing rental transactions, coordinating the flow of data between the Model and the View, and triggering appropriate actions based on user interactions. It ensures that the user input is validated and appropriately acted upon, orchestrating the overall functionality and behavior of the movie rental app.

By adopting the MVC architecture, the movie rental app achieves modularity, code reusability, and easier maintenance. The separation of concerns enables developers to work independently on different components, allowing for better collaboration and development efficiency. Changes in one component can be made without affecting the others, making it easier to test, debug, and enhance specific parts of the application. Moreover, the MVC architecture promotes scalability and extensibility, as new features or modifications can be incorporated without disrupting the existing functionality, facilitating the continuous evolution of the movie rental app to meet the changing needs of its users.

### 4.3. Components Design

#### 4.3.1. Users Interface:

- Users are able to access:
  - Home Page
  - Feature Movies Page
  - Movie Pages
  - TV Shows Page
  - Show Pages
  - Profile Pages
  - Login/Register Pages
  - Search Page

#### 4.3.2. Authentication Interface:

- The authentication interface and features of SmashBruh are as follows:
  - Local Authenticate:
  - Using cookie-based mechanism
  - The token will be create base on user’s ID
  - Using JWT as first layer of hash and to adding the expire date
  - One version of token will be hash layer 2 using bcrypt and save to database before set that token to user’s cookie. So that even attacker welly understand the authenticate mechanism, they can’t fake the token to access user’s account
- oAuth2:
  - Support 3 oAuth2 provider: google, github, facebook
  - Working flow:
  - User will be redirect to path /auth/<provider> of back-end URL and then the back-end will redirect user to provider’s oAuth2 page.
  - After successful login, provider will redirect user to path /auth/<provider>/callback on back-end. At this point, if user is exist, then it will update user’s data such as avatar to match the information from oAuth2 provider. In case user is not exist, server will create user based on oAuth2 provider information
  - Then it will redirect user back to front-end on path /auth/<provider> also add hashed user’s ID(on oAuth2 provider database) to session
  - Front-end will sent a get request from path /auth/<provider> to back-end path /login/<provider> (the session will be auto attached)
  - If the user’s Id is matched, server will create an token and the flow continue as same as Local Authenticate mechanism.

#### 4.3.3. Administration Interface:

Regarding our admin's interface, it is important to note that there is room for improvement and the addition of more functionalities. With that being said, in the Movie and TV Shows pages, when viewing a specific ID, the admin will have an additional tool located next to the "Favourite" and "Rate" icons. This tool will enable the admin to make a movie or TV show available to the public and users. More details about this functionality will be covered in the Data Schema and Model section.

<img  src="Images/others/admin_page_1.png" alt="Admin page 1" width="1000">

To access the Admin page, users need to click on the Admin icon present in the User popup within the Navbar. However, it is worth mentioning that the Admin icon will only be visible if the user is an admin.

<img  src="Images/others/admin_page_2.png" alt="Admin page 2" width="1000">

The Admin page will display the available movies and TV shows, providing an easier management interface for admins. It is important to acknowledge that this functionality can be expanded further to incorporate additional features, which will be discussed in the Future Work section.

<img  src="Images/others/admin_page_3.png" alt="Admin page 3" width="1000">

### 4.4. Structure and Relationships

- User:

  - Description:
    - In our website, a user can rent, rate and like as many movies or TV shows as they like, so we have built our database which revolve around such requirements. A user document is linked with 3 other documents, which are User's favorite, rental and ratings.
  - Relationship:
    - A user can have many rentals (one-to-many relationship)
    - A user can like many rentals (one-to-many relationship)
    - A user can rate many rentals (one-to-many relationship)

- Movie/Show:

  - Description:
    - Since there are more than thousands of movies and TV shows current, in order to accurately and realistically access the information, we have opted to use an online movie and show database to fetch information. This means that there are no documents to store all of the movies and shows. Instead, we only fetch what we need, and store them.
  - Relationship:
    - A movie/show can be associated with one user, user rating, user order and user favorite (one-to-one relationship)

- History:
  - Description:
    - When a user search on the web page, a copy of the search string is saved to the database to enhance the user's experience.
  - Relationship:
    - A user can have many searched strings, and a searched string can belong to many users (many-to-many relationship)

### 4.5. Data Model:

- Schema: user
  - firstName, lastName<String>: The name of the user
  - password<String>: the user’s password, hashed using bcrypt library
  - picturepath<String>: the user’s profile pictures
  - verified<bool>: a value to determine whether the user has been verified or not
  - token<String>: a token used for session control
  - FbId, GgId, ghId<String>: Data for using Oauth2 with Facebook, Google and GitHub

<img src="Images/schema/schema_1.png" alt="Schema 1" width="1000">

- Schema: user-movie favorites
  - userID<String>: the ID of a valid user
  - movieID<String>: the ID of a movie or show
  - media_type<String>: Used to distinguish between movies and shows. The API we are using can have 2 duplicate ID, so specifying the type is necessary

<img src="Images/schema/schema_2.png" alt="Schema 2" width="1000">

- Schema: user-movie ratings
  - userID, movieID, media_type: Similar to user-movie favorites
  - Rating<int>: store the user’s rating
  - season<int>: an additional index that store the season of a TV show, if the rental was a movie, then this index value is 0

<img src="Images/schema/schema_3.png" alt="Schema 3" width="1000">

- Schema: user-movie rentals
  - userID, movieID, media_type, season: Similar to user-movie favorites
  - rentalBeginDate, rentalExpireDate<date>: store the date the movie/show was rented, and the expire date

<img src="Images/schema/schema_4.png" alt="Schema 4" width="1000">

- Schema: user-searches
  - userID: Similar to user-movie favorites
  - searchedString<String>: Store a search string, when a user searches something, a new document of this type is created.

<img src="Images/schema/schema_5.png" alt="Schema 5" width="1000">

- Schema: movie-availability
  - movieID, media_type, season: Similar to user-movie favorites
  - isAvailable: To specify whether a particular movie or show can be rented or not. This index can only be edited by SmashBruh’s admin.
    <img style="display: block; 
                margin-left: 150;
                margin-right: 150;
                width: 100%;" 
          src="Images/schema/schema_6.png" alt="Schema 6" width="1000">

### 4.6. GUI

#### 4.6.1. Login Screen

| Identification | Login Module                                                                                                                        |
| :------------- | :---------------------------------------------------------------------------------------------------------------------------------- |
| Type           | User Interface                                                                                                                      |
| Purpose        | The Login module provides a secure and authenticated login screen for user to access the website                                    |
| Subordinates   | None                                                                                                                                |
| Dependencies   | The system must be connected to the database to verify user’s credentials, access permissions and register a new account            |
| Interfaces     | The module will have buttons and fields for user to log in and sign up                                                              |
| Resources      | The module requires a user interface for users to provide their information and backend system to validate and register new account |
| Processing     | The module processes user’s requests to access the webpage, verifying their credentials and access permission                       |
| Data           | The module validate user’s login account and register for a new one                                                                 |
|                |

<img src="Images/pages/login_page.jpeg" alt="GUI 1" width="1000">

#### 4.6.2. Homepage

| Identification | Home Page Module                                                                                                            |
| :------------- | :-------------------------------------------------------------------------------------------------------------------------- |
| Type           | User Interface                                                                                                              |
| Purpose        | Allows user to access different movies and TV Shows                                                                         |
| Subordinates   | None                                                                                                                        |
| Dependencies   | The system must be connected to the database and retrieve movies and TV shows using API from TMDB                           |
| Interfaces     | The module has a navigation bar with buttons to route to another pages and movie and shows card for user to choose          |
| Resources      | The module requires database and information from TMDB API                                                                  |
| Processing     | The module processes user’s requests to view a specific film or TV series, retrieving data from the database and present it |
| Data           | The module retrieves movie and TV shows information from the database                                                       |
|                |

<img src="Images/pages/home_page.jpeg" alt="GUI 2" width="1000">

#### 4.6.3. Feature Movies

| Identification | Movie Module                                                                                                   |
| :------------- | :------------------------------------------------------------------------------------------------------------- |
| Type           | User Interface                                                                                                 |
| Purpose        | Allow user to access different movies                                                                          |
| Subordinates   | None                                                                                                           |
| Dependencies   | The system must connect to the database using TMDB API to retrieve movies                                      |
| Interfaces     | The module display movies with different criteria                                                              |
| Resources      | The module requires database and information from TMDB API                                                     |
| Processing     | The module processes user’s requests to view a specific film and retrieve data from the database to present it |
| Data           | The module retrieves movie information from the database                                                       |
|                |

<img src="Images/pages/feature_movies_page.jpeg" alt="GUI 3" width="1000">

#### 4.6.4. TV Shows

| Identification | Show Module                                                                                                         |
| :------------- | :------------------------------------------------------------------------------------------------------------------ |
| Type           | User Interface                                                                                                      |
| Purpose        | Allows user to access different TV shows                                                                            |
| Subordinates   | None                                                                                                                |
| Dependencies   | The system must connect to the database using TMDB API to retrieve movies                                           |
| Interfaces     | The module display TV shows with different criteria                                                                 |
| Resources      | The module requires database and information from TMDB API                                                          |
| Processing     | The module processes user’s requests to view a specific TV series and retrieve data from the database to present it |
| Data           | The module retrieves TV shows information from the database                                                         |
|                |

<img src="Images/pages/tv_shows_page.jpeg" alt="GUI 4" width="1000">

#### 4.6.5. My Lists

| Identification | List Module                                                                                                           |
| :------------- | :-------------------------------------------------------------------------------------------------------------------- |
| Type           | User Interface                                                                                                        |
| Purpose        | Allow users to access their favorited and rented movies and TV series                                                 |
| Subordinates   | None                                                                                                                  |
| Dependencies   | The system must connect to the database to get user favorite and rented movies and tv shows as well as using TMDB API |
| Interfaces     | The module display user favorite and rented movies and TV series                                                      |
| Resources      | The module requires database and information from TMDB API                                                            |
| Processing     | The module retrieve user favorite and rented movies or tv shows from the database and display them                    |
| Data           | The module retrieve information from user’s database schema                                                           |
|                |

<img src="Images/pages/my_list_page.jpeg" alt="GUI 5" width="1000">

#### 4.6.6. Profile Page

| Identification | Profile Module                                                                 |
| :------------- | :----------------------------------------------------------------------------- |
| Type           | User Interface                                                                 |
| Purpose        | Allow user to access and modify profile page                                   |
| Subordinates   | None                                                                           |
| Dependencies   | The system must connect to the database to get user information                |
| Interfaces     | The module has fields displaying user’s information and buttons to change them |
| Resources      | The module requires user database schema                                       |
| Processing     | The module retrieve user’s information from the database and display them      |
| Data           | The module retrieve information from user’s database schema                    |
|                |

<img src="Images/pages/profile_page.jpeg" alt="GUI 6" width="1000">

#### 4.6.7. Movie Page

| Identification | Movie Page Module                                                                                                                                                          |
| :------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Type           | User Interface                                                                                                                                                             |
| Purpose        | Allow user to view a movie’s further information, to rate a movie and to like and add it into their list                                                                   |
| Subordinates   | None                                                                                                                                                                       |
| Dependencies   | The system must connect to the database to get user information and TMDB API to fetch a movie’s information                                                                |
| Interfaces     | The module display the movie’s trailer and information, buttons to like and favorite and recommendations                                                                   |
| Resources      | The module requires user database schema                                                                                                                                   |
| Processing     | The module retrieve user’s information from the database and display the rating and whether they like it or not as well as using TMDB API to fetch and display information |
| Data           | The module retrieve information from user’s database schema and TMDB api                                                                                                   |
|                |

<img src="Images/pages/movie_page_1.jpeg" alt="GUI 7" width="1000">

<img src="Images/pages/movie_page_2.jpeg" alt="GUI 8" width="1000">

#### 4.6.8. TV Page Module

| Identification | TV Page Module                                                                                                                                                             |
| :------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Type           | User Interface                                                                                                                                                             |
| Purpose        | Allow user to view a series’s further information, to rate a series and to like and add it into their list                                                                 |
| Subordinates   | None                                                                                                                                                                       |
| Dependencies   | The system must connect to the database to get user information and TMDB API to fetch a show’s information                                                                 |
| Interfaces     | The module display the TV show’s trailer and information, buttons to like and favorite and recommendations                                                                 |
| Resources      | The module requires user database schema                                                                                                                                   |
| Processing     | The module retrieve user’s information from the database and display the rating and whether they like it or not as well as using TMDB API to fetch and display information |
| Data           | The module retrieve information from user’s database schema and TMDB api                                                                                                   |
|                |

<img src="Images/pages/show_page_1.jpeg" alt="GUI 9" width="1000">

<img src="Images/pages/show_page_2.jpeg" alt="GUI 9" width="1000">

### 4.7. Functionality Design

- Key features:

  - View movies/shows: display information of available movies/shows on the internet at the moment.
  - Favourite: press heart button and that movies/shows are stored inside collections of favourites of everything.
  - Rent: rent a movie or show for a period of time then the movie or show automatically expires after the expiration day of the movie or show is exceeded.
  - Rate: rate a movie or show for a number of stars and it is stored in the database storage of individuals.

- Other features:

  - Search and History searched: find what users are interested in and what you searched will remain in your history up to 5 most recent searches
  - My list: where you can view your liked movies or tv shows
  - Recommendation: recommend based on the genres, cast of movies or shows accessed at real-time by users on any given movie and show page.

## 5. Implementation

### 5.1. File Structure

```
C:.
|   .gitlab-ci.yml
|   package-lock.json
|   README.md
|
+---documents
|   |   DatabaseDiagram.png
|   |   file_structure.txt
|   |   report.md
|   |
|   +---Images
|   |   |   ColorPalette.png
|   |   |   FeatureMoviePage.png
|   |   |   heart_movie.png
|   |   |   HomePage.png
|   |   |   home_page.png
|   |   |   home_page_2.png
|   |   |   InfoMyList.png
|   |   |   login.png
|   |   |   LoginPage.png
|   |   |   movie-page-2.png
|   |   |   movie-page.png
|   |   |   MoviePage.png
|   |   |   my_list.png
|   |   |   my_list_2.png
|   |   |   NoInfoMyList.png
|   |   |   ProfilePage.png
|   |   |   rate_movie.png
|   |   |   rent_movie.png
|   |   |   SearchPage.png
|   |   |   search_movie.png
|   |   |   ShowPage.png
|   |   |   TVShowsPage.png
|   |   |
|   |   +---deploy
|   |   |       deploy_1.png
|   |   |       deploy_2.png
|   |   |       deploy_3.png
|   |   |
|   |   +---others
|   |   |       admin_page_1.png
|   |   |       admin_page_2.png
|   |   |       admin_page_3.png
|   |   |       file_structure_1.png
|   |   |       file_structure_2.png
|   |   |
|   |   +---pages
|   |   |       feature_movies_page.jpeg
|   |   |       home_page.jpeg
|   |   |       login_page.jpeg
|   |   |       movie_page_1.jpeg
|   |   |       movie_page_2.jpeg
|   |   |       my_list_page.jpeg
|   |   |       profile_page.jpeg
|   |   |       search_page.jpeg
|   |   |       show_page_1.jpeg
|   |   |       show_page_2.jpeg
|   |   |       tv_shows_page.jpeg
|   |   |
|   |   \---schema
|   |           schema_1.png
|   |           schema_2.png
|   |           schema_3.png
|   |           schema_4.png
|   |           schema_5.png
|   |           schema_6.png
|   |
|   +---Sequence
|   |       AdminSequenceDiagrams.png
|   |       UserSequenceDiagrams.png
|   |
|   \---UseCases
|       \---User
|               1. Sign Up Use Case.docx
|               2. Sign In Use Case.docx
|               3. Choose Movie Use Case.docx
|               4. Search Use Case.docx
|               UserUseCaseDiagrams.png
|
+---server
|   |   .babelrc
|   |   .dockerignore
|   |   .env
|   |   .env.example
|   |   .gitignore
|   |   Dockerfile
|   |   index.js
|   |   package-lock.json
|   |   package.json
|   |
|   +---config
|   |       ViewEngine.js
|   |
|   +---controller
|   |       admin.js
|   |       auth.js
|   |       movieAPI.js
|   |       MovieAvailability_Controller.js
|   |       oAuth2_Controller.js
|   |       SampleController.js
|   |       user.js
|   |       UserFavouriteMovie_Controller.js
|   |       UserRateMovie_Controller.js
|   |       UserRentMovie_Controller.js
|   |       UserSearchHistory_Controller.js
|   |
|   +---middleware
|   |       AdminPermission.js
|   |       auth.js
|   |       FileUploader.js
|   |
|   +---models
|   |       AdminChecker_model.js
|   |       EmailVerification_Schema.js
|   |       MovieAvailability_Model.js
|   |       MovieAvailability_Schema.js
|   |       oAuth2_model.js
|   |       sample.js
|   |       UserFavouriteMovie_Model.js
|   |       UserFavouriteMovie_Schema.js
|   |       UserRateMovie_Model.js
|   |       UserRateMovie_Schema.js
|   |       UserRentMovie_Model.js
|   |       UserRentMovie_Schema.js
|   |       UserSearchHistory_Model.js
|   |       UserSearchHistory_Schema.js
|   |       User_Schema.js
|   |
|   +---public
|   |   \---assets
|   |
|   +---routes
|   |       WebRoutes.js
|   |
|   \---__test__
|           mock_TMDB.js
|           webRoutes.test.js
|
\---views
    |   api.yaml
    |   package-lock.json
    |   verified.html
    |
    +---React
    |   |   .babelrc
    |   |   .dockerignore
    |   |   .env
    |   |   .eslintrc.cjs
    |   |   .gitignore
    |   |   Dockerfile
    |   |   index.html
    |   |   jsconfig.json
    |   |   package-lock.json
    |   |   package.json
    |   |   vercel.json
    |   |   vite.config.js
    |   |
    |   +---src
    |   |   |   App.css
    |   |   |   App.jsx
    |   |   |   index.css
    |   |   |   main.jsx
    |   |   |   theme.js
    |   |   |
    |   |   +---assets
    |   |   |   |
    |   |   |   +---image
    |   |   |   |
    |   |   |   \---images
    |   |   |
    |   |   +---components
    |   |   |       FlexBetween.jsx
    |   |   |       Loading.jsx
    |   |   |       ScreenSpinner.jsx
    |   |   |       UserImage.jsx
    |   |   |
    |   |   +---scenes
    |   |   |   +---adminPage
    |   |   |   |       index.jsx
    |   |   |   |
    |   |   |   +---featurePage
    |   |   |   |       featureCard.jsx
    |   |   |   |       featureList.jsx
    |   |   |   |       index.jsx
    |   |   |   |
    |   |   |   +---homePage
    |   |   |   |       BackgroundAnimation.jsx
    |   |   |   |       Carousel.jsx
    |   |   |   |       HomeList.jsx
    |   |   |   |       index.jsx
    |   |   |   |       MovieCard.jsx
    |   |   |   |       ShowDiscoveryCard.jsx
    |   |   |   |
    |   |   |   +---loginPage
    |   |   |   |       index.jsx
    |   |   |   |       NewDesign.jsx
    |   |   |   |
    |   |   |   +---moviePage
    |   |   |   |       index.jsx
    |   |   |   |
    |   |   |   +---mylistPage
    |   |   |   |       index.jsx
    |   |   |   |
    |   |   |   +---navbar
    |   |   |   |       IconListComponent.jsx
    |   |   |   |       index.jsx
    |   |   |   |       SearchBar.jsx
    |   |   |   |       Searchbar2.jsx
    |   |   |   |
    |   |   |   +---profilePage
    |   |   |   |   |   EmailVerifyDialog.jsx
    |   |   |   |   |   index.jsx
    |   |   |   |   |   NewDesign.jsx
    |   |   |   |   |   Original.jsx
    |   |   |   |   |   PaymentDialog.jsx
    |   |   |   |   |   ProfileSection.jsx
    |   |   |   |   |   StarAnimation.jsx
    |   |   |   |   |   UserImage.jsx
    |   |   |   |   |
    |   |   |   |   \---PurchaseCard
    |   |   |   |           PurchaseCard.jsx
    |   |   |   |           PurchaseCard2.jsx
    |   |   |   |           PurchaseCard3.jsx
    |   |   |   |           PurchaseCard4.jsx
    |   |   |   |           PurchaseCard5.jsx
    |   |   |   |           PurchaseCard6.jsx
    |   |   |   |
    |   |   |   +---searchPage
    |   |   |   |       index.jsx
    |   |   |   |
    |   |   |   +---showPage
    |   |   |   |       index.jsx
    |   |   |   |
    |   |   |   +---trailerPlayer
    |   |   |   |       carouselVideo.jsx
    |   |   |   |       YoutubeVideo.jsx
    |   |   |   |
    |   |   |   \---tvPage
    |   |   |           index.jsx
    |   |   |           tvCard.jsx
    |   |   |           tvList.jsx
    |   |   |
    |   |   \---states
    |   |           index.js
    |   |
    |   \---__test__
    |           profile.test.js
    |
    \---Sample
            test.ejs
```

Our file and folder structure closely follows the Model-View-Controller (MVC) pattern. At the root level, we have three main folders: "documents," "server," and "views."

In the "documents" folder, we store various reports, use cases, and diagrams. The "images" folder within it contains all the images and pictures used in the Markdown report. Additionally, we have the "sequence" and "UseCases" folders, which hold the corresponding diagrams for our application. This is also where the main project report can be found.

The "server" folder contains the server code or backend of our project. Inside, there is a "test" folder housing two test cases for our pipelines and CI/CD in GitLab. The "config" folder includes a single Javascript file called "ViewEngine.js," responsible for configuring our Express backend server.

The two most significant folders following the MVC model are "controller" and "model":

- The "model" folder contains Javascript files ending in "\_Schema.js," which define the schemas of our application, specifying the fields and restrictions. Files ending in "\_Model.js" encapsulate the logic for retrieving, updating, deleting, or inserting records into these schemas. The model and schema files work together closely. For example, we may have a schema and model code for storing a user's favorite movies and TV shows.

<img  src="Images/others/file_structure_1.png" alt="File Structure 1" width="1000">

<img  src="Images/others/file_structure_2.png" alt="File Structure 2" width="1000">

- The "controller" folder contains files ending in "\_Controller.js" that act as an interface between the backend server and our MongoDB database. They directly interact with the model files in the "model" folder mentioned earlier. While the model files contain the actual logic for interacting with the corresponding schemas, the controller files handle the calls to those model files from the server side. Files not ending in "\_Controller.js" contain the logic for most of our APIs that don't interact with MongoDB. For instance, "movieAPI.js" manages the logic for retrieving movie and TV show details directly from The Movie Database's API, rather than our own database.

Other notable folders include:

- "Middleware": This folder holds the logic for our middleware functions in routes. For example, "auth.js" handles token authentication for users, while "AdminPermission.js" verifies admin clearance for certain routes.
- "public": This folder contains static files served directly to clients. In our case, it includes user images and avatars, which can be sent to the frontend via an API route.
- "routes": Within this folder, we have a single file called "WebRoutes.js" that serves as the essential file for all our API routes. It is organized in a way that enhances readability and provides clarity for our routes.
- The remaining files in the "server" folder mostly pertain to Docker, Git, and Node modules management. However, "index.js" stands out as the main file for the backend server. It imports all the necessary files and modules to keep the server running smoothly.
- Inside the "React" folder, we can find the "test" directory that houses our test cases for pipelines in GitLab. Moving on, the "src" folder contains the design code and implementation for the view of our web application. Within "src," we have the following sub-folders:
- "assets": Similar to the backend folders, this directory holds all static files such as images and color schemes for the design and UI department.
- "components": This folder contains reusable React components that are used throughout our app, such as the loading screen animation and user's avatar image.
- "scenes": It includes the design and implementation for all pages, ranging from the login page to the home page and profile page.
- "states": This folder manages the state of our application using Redux, an open-source JavaScript library. The state includes "user" information for easier data retrieval, "token" for authorization in routes, and "mode" for light and dark mode.
- "main.jsx": This file serves as our main frontend application file.
- "index.css": It sets global styles that apply to the "main.jsx" file, representing our entire frontend application.
- "App.jsx" and "App.css": "App.jsx" is our main React application component and is contained within "main.jsx". It plays a crucial role as it encompasses all our React components, including the aforementioned pages, and holds important configurations and authentication/authorization logic throughout our frontend view application.
- "theme.js": This file contains color tokens and theme settings used in our web application for specific UI design styles and color schemes.
- The remaining files in the "React" folder pertain to configurations for Docker, Git, Vite, Node module management, and Vercel deployment.

In conclusion, we adhere to a file and directory structure that closely resembles the MVC (Model-View-Controller) pattern for our backend, and we follow a conventional and widely-used structure for our frontend. However, there are some errors that need to be corrected and areas where improvements can be made, particularly in terms of naming conventions and removing redundant files and folders. By addressing these issues, we can enhance the overall organization and efficiency of our codebase.

### 5.2. Development Environment and Technology Stack

The development of SmashBruh Movie Renting Website requires a robust and efficient development environment to ensure the smooth creation and deployment of the platform. Here's an overview of the key components of the development environment:

- Programming Languages: JavaScript takes center stage in the development process of the SmashBruh movie renting website. As a dynamic and versatile programming language, JavaScript empowers the website with interactivity and functionality. It enables features like seamless search functionality, dynamic recommendations, interactive elements, and smooth navigation. JavaScript's integration with backend APIs ensures efficient data retrieval and real-time updates.
- Frameworks and Libraries:
  We decided to use a combination of libraries and database to assist us in implementing the app. The combination or MERN stack, consists of Node.js - a premier JavaScript web server, Express.js - a Node.js web framework, React - a client-side JavaScript framework and MongoDB - a document database. The middle or application tier of our system is built using Express and Node. Express.js serves as the server-side web framework, while Node.js acts as the robust and widely adopted JavaScript server platform. Together, these technologies form a powerful foundation for developing and delivering web applications. Express provides a streamlined and efficient framework for handling web requests and managing routes, while Node enables the execution of server-side JavaScript code, allowing for scalable and high-performance server applications.
- Database Management System:
  MongoDB, a popular NoSQL database management system, serves as the foundation for storing and managing data in the SmashBruh movie renting website. MongoDB offers a flexible and scalable approach to data storage, making it ideal for handling movie information, user profiles, rental history, and other pertinent data.
- Version Control System:
  With Git and GitLab, SmashBruh benefits from features like branch management, version control, and the ability to roll back changes if needed. This combination ensures that the development team can work concurrently, seamlessly integrate new features, resolve conflicts, and track the evolution of the codebase.
- Development Tools and Integrated Development Environment (IDE): With its intuitive interface and customizable settings, developers working on SmashBruh can personalize their coding environment according to their preferences. VS Code provides essential tools such as syntax highlighting, code completion, and linting, ensuring clean and error-free code. The built-in debugger enables efficient troubleshooting and debugging, helping to identify and fix issues quickly.
- Cloud Services: Leveraging cloud services can provide scalability, flexibility, and reliability to the website. We were able to achieve by using Vercel - a serverless platform for static and hybrid applications.
- Security Measures: Implementing robust security measures is vital to safeguard user data and protect against potential threats. This includes secure coding practices, user verification and authentication mechanisms, and also adherence to industry-standard security protocols.
- Continuous Integration and Deployment: With the help of GitLab, our implementation of CI/CD (Continuous Integration/Continuous Deployment) pipeline ensures integration of code changes, automated testing, and efficient deployment to staging and production environments.

By establishing a comprehensive development environment encompassing these components, SmashBruh can ensure efficient development processes, high-quality code, and a scalable platform that meets the needs and expectations of clients

### 5.3. CI/CD Testing, Docker and Deployment

The CI/CD pipeline automates the testing, building, and deployment of the application, ensuring efficient and reliable software delivery. The pipeline described in this document utilizes GitLab CI/CD and Docker for containerization.
The CI/CD pipeline consists of three stages: test, build and deploy. Information about each stage in detail:

#### 5.3.1. Test Stage:

- Environment: The test stage uses the node: 16 Docker image as the execution environment.
- Actions:
  - The pipeline changes the directory to views/React, removes existing node-modules and package-lock.json files, and installs dependencies using `npm install`.
  - Then, it runs the tests using the `npm test command`.
  - The test will run through the paths of our application and check whether the status code is returned right as expected. The test also check if React component is rendered correctly.

<img  src="Images/deploy/ci_cd_1.png" alt="CI CD 1" width="1000">

<img  src="Images/deploy/ci_cd_2.png" alt="CI CD 2" width="1000">

#### 5.3.2. Build Stage:

- Environment: The build stage utilizes the docker image and the docker:dind service, allowing Docker commands within the job. This stage involves two actions: constructing the server application image and creating the client application image.
- Actions:
  - For the build-server-image job:
    - The pipeline changes the directory to the server
    - It performs a Docker login to the specified registry using the provided credentials.
    - The server image is built using docker build, tagged with the specified names and tags, and pushed to the registry.
  - For the build-client-image job:
    - The pipeline changes the directory to views/React.
    - It performs a Docker login to the specified registry using the provided credentials.
    - The client image is built using docker build, tagged, and pushed to the registry.

#### 5.3.3. Deploy Stage:

- The deploy stage follows the build stage and is responsible for deploying the application to the Vercel app.
- Deploy Stage Configuration:
  - Environment: The deploy stage utilizes the Vercel app integration, which requires setting up appropriate environment variables in the Vercel app.
  - Actions: When a new commit is pushed to GitLab, the pipeline initiates the deployment process by interacting with the Vercel app.
- Deploying to Vercel:
  - The pipeline integrates with the Vercel app, which allows for easy and automated deployment of the Node.js application.

In addition to the existing CI/CD pipeline stages, there is a specific section dedicated to deploying the backend of the application to the Render app. Due to limitations in the free tier of the Render app, automated deployment of the latest backend commit is not possible. Therefore, the deployment process for the backend needs to be done manually by deploying the most recent commit.

<img  src="Images/deploy/deploy_1.png" alt="Schema 1" width="1000">

<img  src="Images/deploy/deploy_2.png" alt="Schema 2" width="1000">

<img  src="Images/deploy/deploy_3.png" alt="Schema 3" width="1000">

### 5.4. API Utilization

#### 5.4.1. Movies

| API                | Purpose                                                                                           | Request Type | Parameter      |
| ------------------ | ------------------------------------------------------------------------------------------------- | ------------ | -------------- |
| getDetail          | allows you to retrieve detailed information about a movie based on its unique movieID.            | GET          | movieID        |
| getTrailerID       | allows you to retrieve the trailer ID(s) of a movie based on its unique movieID.                  | GET          | movieID        |
| getRecommendations | allows you to retrieve movie recommendations based on a specific movie identified by its movieID. | GET          | movieID        |
| getMovieCredits    | allows you to retrieve the credits or cast information of a movie based on its unique movieID.    | GET          | movieID        |
| getList            | allows you to retrieve a list of movies based on a specified category.                            | GET          | category, page |
|                    |                                                                                                   |              |

#### 5.4.2. TV Shows

| API                    | Purpose                                                                                        | Request Type | Parameter      |
| ---------------------- | ---------------------------------------------------------------------------------------------- | ------------ | -------------- |
| getShowDetail          | allows you to retrieve detailed information about a tv show based on its unique showID.        | GET          | showID         |
| getShowTrailerID       | API endpoint allows you to retrieve the trailer ID(s) of a show based on its unique showID.    | GET          | showID         |
| getShowRecommendations | allows you to retrieve show recommendations based on a specific show identified by its showID. | GET          | showID         |
| getShowCredits         | allows you to retrieve the credits or cast information of a show based on its unique showID.   | GET          | showID         |
| getShowList            | allows you to retrieve a list of tv shows based on a specified category.                       | GET          | category, page |
|                        |                                                                                                |              |

#### 5.4.3. Discovery

| API               | Purpose                                                                                                           | Request Type | Parameter |
| ----------------- | ----------------------------------------------------------------------------------------------------------------- | ------------ | --------- |
| getMovieDiscovery | allows you to retrieve a list of movies based on discovery parameters, enabling users to discover popular movies. | GET          | page      |
| getShowDiscovery  | allows you to retrieve a list of tv shows based on discovery parameters, enabling users to discover top shows.    | GET          | page      |
| getImageCarousel  | allows you to retrieve a list of movies suitable for displaying in an image carousel or slideshow                 | GET          | 🚫        |
| getAnimeDiscovery | allows you to retrieve a list of anime based on discovery parameters, enabling users to discover popular anime.   | GET          | page      |
|                   |                                                                                                                   |              |

<img  src="Images/others/swagger_doc.jpeg" alt="swagger doc 1" width="1000">

## 6. User/Admin Getting Started Guide

### 6.1. User

To guide you through using our web application as a user, we provide two options: using our example user account or creating your own account. Please follow the steps below:

1. Create an Account (Optional):
   To access all the features and benefits of SmashBruh, start by creating your account. Click on the "Sign Up" button on the homepage and provide the required information, including your name, email address, and a secure password. Once you've filled in the details, click "Finish" to proceed.

2. Accessing the Application:
   Go to our web application's login page and fill in your information. It is recommended that you use our example user account to get the full feeling of our app. Enter the following example user account credentials:
   Email: userexample@gmail.com
   Password: 123123123

3. Explore Movie Catalog:
   After successfully creating your account, it's time to explore our extensive movie catalog. Navigate to the "Feature Movies" or "Shows" section to discover a wide range of genres. Browse through the collections, popular releases, or use the search bar to find specific movies.

4. Select and Rent Movies:
   When you find a movie you want to rent, click on its title to access the movie details page. Here, you'll find a synopsis, cast and crew information, user reviews, and other relevant details. Click on "Rent" to proceed to the checkout. You can also "favourite" a movie and rate them with the corresponding icons.

5. Make Payment:
   At the checkout, review your selected movie and rental duration. SmashBruh provides secure payment options. Choose your preferred payment method, enter the required details, and click "Smash" to finalize your rental.

6. Enjoy Your Movie:
   Once the payment is processed successfully, you'll receive a confirmation message along with access to the movie. Head to the "My Rentals" section, where you'll find all the movies you've rented.

7. Manage Your Account:
   SmashBruh provides a user-friendly account management interface to help you keep track of your rentals, update your personal information, and manage your payment methods. Access the "My Profile" section to view and modify your profile, change your password, or update your payment details.

8. Explore Additional Features:
   While movie rentals are at the core of SmashBruh, we offer additional features to your movie-watching experience. Explore our curated playlists, personalized recommendations.

### 6.2. Admin

Getting Started Guide for SmashBruh Movie Renting Website for admins:

1. Accessing the Application:
   Go to our web application's login page and fill in your information. It is a must that you use our example admin account as there are no way to create admin accounts unless you create them directly in our MongoDB. Enter the following example user account credentials:
   Email: adminexample@gmail.com
   Password: 123123123

2. Offer movies and TV shows:
   When in a particular movie or TV show, you can click on the Tool icon to make it available for rental to users. Green icon indicates that the media is currently available and red icon for unavailable media.

3. Management available movies and TV shows:
   By clicking on the Admin icon in the User's popup bar within the Navbar, you are directed to the admin page and can see all the movies and TV shows that are currently rendered available to users.

## 7. Conclusion

### 7.1. Summary of Project

In conclusion, our project aims to assist people in renting movies/shows and keeping track of their favourite movies/shows. Our web application is not a rental platform but it can acts as a middleware from clients to one if implemented correctly. With the The Movie Database as our main API, we can provide you information about every movies and TV shows that you like.

### 7.2. Future Work

- Despite facing time constraints and limited experience working on a large-scale team project, we encountered challenges in meeting deadlines and fully achieving our initial ideas and objectives. However, it is important to acknowledge the significant progress we have made and the invaluable lessons we have learned in the realms of web development and collaborative teamwork. Drawing from these experiences, we can identify future objectives aimed at refining and optimizing the app

- Parental Control System

  - With our vast database of movies and shows, it becomes necessary to address the potential exposure to explicit and graphic content. This concern is particularly crucial when our platform caters to young audiences, as it can lead to harmful interpretations and misuse of media. To mitigate these risks, we prioritize the implementation of a robust parental control system. The parental control system allows registered users to act as parents or guardians and exercise control over the content accessible to their children. By enabling this feature, explicit and inappropriate content can be effectively filtered out. This ensures that young users are protected from encountering material that is not suitable for their age group or could have a negative impact.

- Further Admin's Interface

  - Despite implementing an admin checking function and establishing a conducive work environment within the database for administrators, we currently lack dedicated admin interfaces for them to efficiently operate and moderate the system. To address this limitation, it is crucial to develop a comprehensive admin interface that offers an extensive range of functionalities. The interface should provide an overview of user information and rental details, enabling administrators to gain insights and perform necessary actions. Examples of these actions include the ability to ban or un-ban users, disable specific movies from being rented or viewed, and execute other administrative tasks. By providing a robust and user-friendly admin interface, we empower administrators with the tools they need to effectively carry out their responsibilities and streamline their workflow.

- Interactive Movie Discussion

  - Introduce a feature where users can engage in discussions, comment on movies, and participate in forums or live chats with other movie enthusiasts.

- Social Integration

  - Integrate social media features that allow users to share their favorite movies, reviews, and recommendations with friends.

- Augmented Reality (AR) Movie Posters

  - Users can scan movie posters using their smartphones or tablets and access interactive content such as trailers, behind-the-scenes footage, or exclusive interviews with the cast and crew.

### 7.3. References

- Color Palette: https://colorhunt.co/palette/060047b3005ee90064ff5f9e
- GitLab: https://gitlab.com/galvdat/vgutinyprojects/pe2023/vgupe2023team5
- MongoDB: https://www.mongodb.com/
- MUI Library: https://mui.com/material-ui/getting-started/overview/
- OAuth2: https://oauth.net/2/

<p style="text-align: right;">©️ Vinh Nguyen Ngoc</p>
