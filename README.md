# airbnb-clone-project

## Project Overview
This project is an Airbnb clone, designed to provide a robust and scalable foundation for managing user interactions, property listings, bookings and payment processing.

## Project Goals

### 1. User Management
- Implement secure user registration, authentication, and profile management.
- Ensure role-based access control for different user types.

### 2. Property Management
- Enable users to create, update, and retrieve property listings.
- Implement search and filtering options for properties.

### 3. Booking System
- Provide a seamless booking experience for users.
- Allow users to manage and modify their bookings.

### 4. Payment Processing
- Integrate a secure payment system for handling transactions.
- Store and manage payment details efficiently.

### 5. Review System
- Let users leave ratings and reviews for properties.
- Implement review moderation and filtering mechanisms.

### 6. Data Optimization
- Ensure efficient database queries and indexing.
- Optimize data retrieval for a smooth user experience.

##  Technology Stack

### 1. **Backend Frameworks**
- **Django** – A high-level Python web framework for rapid development and clean design.
- **Django REST Framework** – Provides powerful tools for building and managing RESTful APIs.

### 2. **Database & Data Handling**
- **MySQL** – A reliable, scalable relational database for efficient data storage.
- **GraphQL** – Enables flexible and optimized data querying.

### 3. **Asynchronous Processing & Caching**
- **Celery** – Handles background tasks like notifications and payment processing.
- **Redis** – Used for caching and session management, improving response times.

### 4. **Deployment & Development Tools**
- **Docker** – Ensures consistent development and deployment environments through containerization.
- **CI/CD Pipelines** – Automates testing and deployment processes for seamless integration.

## Team Roles

### 1. Backend Developer
- Responsible for implementing API endpoints, database schemas and business logic.

### 2. Database Administrator 
- Manages database design, indexing, and optimizations.

### 3. DevOps Engineer 
- Handles deployment, monitoring and scaling of the backend services.

### 4. QA Engineer
-Ensures the backend functionalities are thoroughly tested and meet quality standards.

## Database Design
This section outlines the database schema, detailing key entities, their relationships and essential attributes.

# Database Design Summary

### Overview
This document outlines the key entities and relationships in the **Airbnb Clone** database.

## Key Entities
### 1. **Users**
- `user_id` – Unique identifier.
- `name` – User’s full name.
- `email` – Unique contact email.
- `user_type` – Defines if the user is a **Guest** or **Host**

### 2. **Properties** (Listings by hosts)
- `property_id` – Unique identifier.
- `host_id` – References the **Users** table.
- `title` – Property name.
- `location` – Address or city.
- `price_per_night` – Cost per night.

### 3. **Bookings** (Reservations made by guests)
- `booking_id` – Unique identifier.
- `guest_id` – References the **Users** table.
- `property_id` – References the **Properties** table.
- `check_in_date`, `check_out_date` – Stay duration.
- `booking_status` – Booking status (Confirmed, Pending, Cancelled).

### 4. **Payments** (Transactions linked to bookings)
- `payment_id` – Unique identifier.
- `booking_id` – References the **Bookings** table.
- `guest_id` – References the **Users** table.
- `amount` – Total transaction cost.
- `payment_status` – Status (Paid, Pending, Failed).

### 5. **Reviews** (Guest feedback on properties)
- `review_id` – Unique identifier.
- `guest_id` – References the **Users** table.
- `property_id` – References the **Properties** table.
- `rating` – Score (1–5 stars).
- `review_text` – Guest review.

## Entity Relationships
- **Hosts** list multiple **properties**.
- **Guests** book multiple **properties**.
- Each **booking** is linked to a **guest** and a **property**.
- Each **booking** can generate a corresponding **payment**.
- **Guests** leave **reviews** for properties they have booked.
 
## Feature Breakdown
## API Security 
## CI/CD Pipeline
