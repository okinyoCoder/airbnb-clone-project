# AirBnB Clone Project

## Overview
The AirBnB Clone project is a full-stack web development project that aims to recreate the core functionalities of the AirBnB platform. It is designed to demonstrate an understanding of object-oriented programming, web development, RESTful APIs, and deployment principles.

## Project Goals
- Build a command-line interface (CLI) for object creation and data management
- Implement custom classes using Python and OOP principles
- Create a RESTful API for managing data
- Store and retrieve data using a storage engine (File/DB)
- Deploy the web application on a live server

## Tech Stack
- **Backend:** Python
- **Database:** MySQL
- **Deployment:** Docker, Gunicorn, Nginx, and Ubuntu

## Author
Anthony Odhiambo  
https://github.com/okinyoCoder



## Team Roles

Successful execution of the AirBnB Clone project requires collaboration across various team roles. Each team member contributes specialized expertise to ensure the functionality, stability, and usability of the final product.

### 1. Backend Developer
Responsible for building and maintaining the core logic of the application. In this project, backend developers:
- Design and implement Python classes and APIs using Flask.
- Handle server-side logic and data processing.
- Ensure integration with storage engines (e.g., file system or databases).

### 2. Database Administrator (DBA)
Manages the database systems and ensures data integrity. In this project, DBAs:
- Design and optimize database schemas.
- Ensure smooth communication between the application and MySQL database.
- Handle data backup, restoration, and security protocols.

### 3. DevOps Engineer
Automates deployment and manages infrastructure. Responsibilities include:
- Setting up Docker environments, Nginx configurations, and CI/CD pipelines.
- Monitoring application performance.
- Managing servers for hosting and deployment.

### 4. Project Manager
Oversees planning, execution, and progress tracking. Responsibilities include:
- Assigning tasks and ensuring timely delivery.
- Coordinating between developers, designers, and stakeholders.
- Managing communication and documentation.

### 5. QA Engineer / Tester
Ensures that the application meets quality standards. Their tasks include:
- Writing test cases for application features.
- Performing manual and automated testing.
- Reporting bugs and ensuring they are resolved.



## Technology Stack

This project utilizes a modern full-stack development toolkit to efficiently build and deploy a scalable, maintainable AirBnB Clone application.

### 1. Django
A high-level Python web framework that encourages rapid development and clean, pragmatic design.  
**Purpose:** Handles backend logic, URL routing, and RESTful API creation.

### 2. PostgreSQL
A powerful open-source relational database system.  
**Purpose:** Stores structured data such as user accounts, bookings, property listings, and reviews.

### 3. GraphQL
A flexible query language for APIs and a runtime for executing queries by using a type system.  
**Purpose:** Allows clients to request only the data they need, improving API performance and developer experience.

### 4. HTML5
The standard markup language for creating web pages.  
**Purpose:** Provides the structure and content of the frontend interface.

### 5. CSS3
A styling language used to describe the look and layout of web documents.  
**Purpose:** Enhances the visual presentation and responsiveness of the frontend UI.

### 6. JavaScript (Vanilla or Frameworks like React)
A scripting language that enables interactive web pages.  
**Purpose:** Implements dynamic content and enhances user interactions on the frontend.

### 7. Django REST Framework (DRF)
A powerful toolkit built on Django for building Web APIs.  
**Purpose:** Simplifies the creation of RESTful APIs to enable communication between frontend and backend.

### 8. Docker
A platform for developing, shipping, and running applications in isolated containers.  
**Purpose:** Ensures consistent environments across development, testing, and production.

### 9. Git & GitHub
Version control system and hosting platform for source code.  
**Purpose:** Facilitates collaboration, version management, and code sharing among team members.

### 10. CI/CD Pipelines
A high-performance web server and reverse proxy.  
**Purpose:** Automated pipelines for testing and deploying code changes.


## Database Design

The AirBnB Clone project relies on a relational database structure that captures the core components of the platform, including users, properties, bookings, payments, and reviews. Below are the main entities, key fields, and their relationships.

### 1. Users
Represents the people who use the platform as either hosts or guests.

**Key Fields:**
- `id`: Unique identifier
- `username`: Login name for the user
- `email`: Contact email
- `password_hash`: Encrypted password
- `is_host`: Boolean indicating if the user can list properties

**Relationships:**
- A user can host multiple properties.
- A user can make multiple bookings.
- A user can leave multiple reviews.

---

### 2. Properties
Represents the listings available for booking.

**Key Fields:**
- `id`: Unique identifier
- `title`: Name or short description
- `description`: Full property description
- `location`: Address or area
- `price_per_night`: Rental price

**Relationships:**
- A property is owned by one user (host).
- A property can have multiple bookings.
- A property can receive multiple reviews.

---

### 3. Bookings
Represents reservations made by guests for a property.

**Key Fields:**
- `id`: Unique identifier
- `user_id`: The guest who made the booking
- `property_id`: The property being booked
- `start_date`: Check-in date
- `end_date`: Check-out date

**Relationships:**
- A booking is made by one user for one property.
- A booking can result in a payment.

---

### 4. Payments
Tracks financial transactions related to bookings.

**Key Fields:**
- `id`: Unique identifier
- `booking_id`: The related booking
- `amount`: Total amount paid
- `payment_method`: Method used (e.g., card, PayPal)
- `status`: Payment status (e.g., completed, pending)

**Relationships:**
- Each payment is linked to one booking.

---

### 5. Reviews
Captures feedback from users about a property after a stay.

**Key Fields:**
- `id`: Unique identifier
- `user_id`: The reviewer
- `property_id`: The reviewed property
- `rating`: Star rating (e.g., 1–5)
- `comment`: Textual feedback

**Relationships:**
- A review is made by one user for one property.

---

### 🔗 Entity Relationships Summary

- **User ⟶ Property**: One-to-Many (a host can own many properties)
- **User ⟶ Booking**: One-to-Many (a guest can make many bookings)
- **Property ⟶ Booking**: One-to-Many (a listing can be booked many times)
- **Booking ⟶ Payment**: One-to-One (each booking has one payment)
- **User ⟶ Review ⟶ Property**: Many-to-One (users can review many properties)



## Feature Breakdown

The AirBnB Clone project replicates essential features of the real AirBnB platform to offer users a full-stack booking experience. Each feature contributes to the overall functionality, user interaction, and business logic of the system.

### 1. User Management
Allows users to register, log in, and manage their profiles. Users can act as guests or hosts, with role-based permissions for listing properties or making bookings.

### 2. Property Management
Hosts can create, update, and delete property listings. Each property includes key details such as location, description, photos, and pricing—making it easier for guests to browse and choose accommodations.

### 3. Booking System
Guests can view availability, select travel dates, and book properties. The system prevents double-booking and ensures that booking rules such as check-in/check-out dates are enforced.

### 4. Payment Integration
Provides secure processing of payments linked to bookings. This feature handles transaction amounts, payment methods, and payment status to ensure financial transparency.

### 5. Review and Rating System
Guests can leave reviews and star ratings for properties they’ve stayed in. This fosters community trust and helps other users make informed booking decisions.

### 6. Search and Filter
Users can search for properties by location, price range, availability, and other criteria. This improves usability and helps users find listings that meet their needs.

### 7. Database Optimizations
Indexing: Implement indexes for fast retrieval of frequently accessed data.
Caching: Use caching strategies to reduce database load and improve performance.




