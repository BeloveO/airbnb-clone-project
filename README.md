# 🏠 airbnb-clone-project
## About the Project
The Airbnb Clone Project is a comprehensive, full-stack, scalable, real-world marketplace web application that allows users to rent out their properties (hosts) and book accommodations (guests), mimicking core functionality of the Airbnb platform.

## 🏆 Project Goals
- ***User Management:*** Implement a secure system for user registration, authentication, and profile management.
- ***Property Management:*** Develop features for property listing creation, updates, and retrieval.
- ***Booking System:*** Create a booking mechanism for users to reserve properties and manage booking details.
- ***Payment Processing:*** Integrate a payment system to handle transactions and record payment details.
- ***Review System:*** Allow users to leave reviews and ratings for properties.
- ***Data Optimization:*** Ensure efficient data retrieval and storage through database optimizations.

## ⚙️ Technology Stack
- **Backend and API Layer:**
  - Framework: Django
  - REST API Framework: Django REST Framework
  - GraphQL(Optional to REST): Graphene Django
- **Database Layer:**
  - Primary Database: PostgreSQL
  - Caching: Redis
  - Search Engine: Elastisearch
- **Frontend Layer:**
  - Web Frontend Framework: React/Angular/VueJS
  - Mobile App Framework: React Native
- *8Task Queue and Background Jobs:**
  - Message Broker and Task Queue: Celery with Redis
- **Real-Time features for Chats and Notifications:**
  - Web Sockets: Django channels
  - Storage Layer for Channels: Redis
- **File Storage:**
  - Static/Media files: Amazon S3 (optional Google Cloud storage)
- **Deployment and DevOps:**
  - Platform-as-a-Service(PaaS): Heroku (optional PythonAnywhere)
  - Optional Infrastructure-as-a-service(IaaS) for more control: AWS/Google Cloud
  - Containerization: Docker
  - CI/CD: GitHub Actions

## 👥 Team Roles
- **Project Manager:** Responsible for handling the timeline and deliverables of the project
- **UI/UX Design:** Responsible for creation of user design, usability testing and prototyping.
- **Frontend Developer:** Responsible for human-centered UI design implementation, state manangement and API integration.
- **Backend Developer:** Responsible for implementing API design and integration, database schemas, and business and server-side logic.
- **Database Administrator:** Manages database design, indexing, and optimizations.
- **DevOps Engineer:** Handles deployment, monitoring, and scaling of the application infrastructure.
- **QA Engineer:** Ensures the final product is bug-free and meets quality standards through thorough testing.

## 💻 Database Design
Key Entities and fields related include:
- **User:** Central entity for both guests and hosts
  - id: AutoField
  - Email: has to be unique
  - first_name
  - last_name
  - date_joined
  - is_host: Boolean field with a false default. To show if user has listing capabilities
- **Listing/Property:** property hosted by user:
  - id: AutoField, PrimaryKey
  - host: user who owns the listing
  - title: short catchy listing qualifier
  - listing_image: Major image advertising the booking
  - description: descrition of the property
  - description_images: multiple images advertising listing
  - address
  - price_per_night
- **Booking/Reservation:** to link guest to listing for a specified period
  - id: AutoField
  - guest: user making the booking
  - listing: property being booked. Made unavailable after booking confirmation
  - check_in_date
  - check_out_date
- **Review:** to gather guest feedback
  - id: AutoField, PrimaryKey
  - booking: to ensure one review per booking
  - author: guest making review
  - rating: ranging from one to five stars for the booking
  - comment: textfield for the author's review
- **Amenities:** provided by the listing and/or host for the property being booked
  - id: AutoField
  - name: name of amenity
  - icon: optional but better for frontend
- **Messaging:** to facilitate communication among users
  - id: AutoField
  - sender
  - receiver
  - content

## 🛠️ Feature Breakdown
- **User Management:** Implement a secure system for user registration, authentication, and profile management.
- **Property/Listing Management:** Develop features for property listing creation, updates, and retrieval.
- **Booking System:** Create a booking mechanism for users to reserve properties and manage booking details.
- **Payment Processing:** Integrate a payment system to handle transactions and record payment details.
- **Review System:** Allow users to leave reviews and ratings for properties.
- **Messaging and Communication system:** allows for in-app direct messaging between users with realtime notifications.
- **Notifications system:** keep users engaged and informed through in-app and email notifications.
- **Data Optimization:** Ensure efficient data retrieval and storage through database optimizations.

## 📈 API Security
#### Authentication: who are you??
- first gatekeeper to ensure the user is who they say they are. This means the usage of Django's built-in authentication system and DRF's authentication classes.
#### Authorization: what you're allowed to do
- after authentication, this controls user's access and permissions allowed. This includes Object level permissions and Role-based access controls.
#### Input Validation and Data Sanitization: Never trust a client's data
- Define strict validation rules for every field and protect against injection attacks using DRF Serializer, SQL Injections(Django ORM) and Django Model Validation
#### HTTPS and Secure communication:
- enforce HTTPS everywhere and use HSTS
#### Throttling and Rate Limiting:
- Protect API from abuse and DoS attacks

## 📌 CI/CD Pipeline
### What is CI/CD?
- **CI(Continuous Integration)**: is the practice of automatically building and testing every change to your codebase as soon as it is pushed to a shared repository. The goal is to catch bugs and integration issues early.
- **CD(Continuous Deployment)**: automates the delivery of code changes to the environment after they pass the CI stage.
### Contribution to this Development Process
For a complex task like this, CI/CD pipeline is important as it serves the following functions:
- Catches bugs early and improve code quality.
- Automates repetitive and error-prone tasks.
- Increases deployment frequency.
- Enables rapid rollback.
### Tools employed for CI/CD Pipeline
- GitHub Actions
- GitLab CI/CD
- CircleCI
- AWS CodePipeline/Google Cloud Build
- Jenkins
