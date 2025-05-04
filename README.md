# AirBnB Clone Project
This project is an application inspired by Airbnb, designed to replicate its core functionalities for property rental and booking. Users can browse available listings, view property details, make reservations, and manage their bookings. Property owners can list new properties, upload images, set prices, and manage reservations.
## Team Roles and Responsibilities
- **Business analyst**: A business analyst in software development acts as a bridge between stakeholders and the development team. They gather and document requirements, analyze business processes, clarify project goals, and ensure the final software solution meets business needs.

- **Project owner**: represents the stakeholders and is responsible for defining the product vision, setting priorities, and making key decisions about features and requirements. They maintain the product backlog, ensure the team is building the right product, and provide feedback throughout development.

- **Project manager**: is responsible for planning, organizing, and overseeing the project to ensure it is completed on time and within budget. They coordinate the team’s work, manage schedules and resources, monitor progress, handle risks and issues, and communicate with stakeholders to keep everyone informed.

- **UI/UX designer**: focuses on creating user interfaces that are visually appealing and easy to use. They design layouts, graphics, and interactive elements (UI), while also researching and testing how users interact with the product to ensure a smooth and satisfying experience (UX).

- **Software architect**: is responsible for designing the overall structure and high-level solutions of the software system. They make key decisions about technologies, frameworks, and patterns to use, ensuring the system is scalable, maintainable, and secure.

- **Software developer**: writes, tests, and maintains the code that brings the project to life. They implement features based on requirements, fix bugs, and collaborate with other team members to ensure the software functions correctly.

- **Quality assurance engineer**: is responsible for testing the software to ensure it works correctly and meets requirements. They design test plans, execute manual and automated tests, identify bugs, and report issues to the team.

- **DevOps engineer**: manages the processes, tools, and infrastructure needed to build, test, deploy, and operate the software efficiently. They automate workflows, set up continuous integration and delivery pipelines, monitor system performance, and handle cloud services or servers.

## Technology Stack Overview
- **Django**: A high-level Python web framework used for building the RESTful API.

- **Django REST Framework**: Provides tools for creating and managing RESTful APIs.

- **PostgreSQL**: A powerful relational database used for data storage.

- **GraphQL**: Allows for flexible and efficient querying of data.

- **Celery**: For handling asynchronous tasks such as sending notifications or processing payments.

- **Redis**: Used for caching and session management.

- **Docker**: Containerization tool for consistent development and deployment environments.

- **CI/CD Pipelines**: Automated pipelines for testing and deploying code changes.

## Database Design Overview
### 1. User
**Important Fields:**
- `id`: Unique identifier
- `name`
- `email`
- `role`: guest, host, or both
- `profile_image_url`

**Relationships:**
- A user can list multiple properties (if a host).
- A user can make multiple bookings (as a guest).
- A user can write multiple reviews.
- A user can receive payments (if a host).

### 2. Property

**Important Fields:**
- `id`: Unique identifier
- `title`
- `description`
- `address`
- `price_per_night`
- `host_id`: Reference to User

**Relationships:**
- A property belongs to one user (the host).
- A property can have multiple bookings.
- A property can have multiple reviews.

### 3. Booking

**Important Fields:**
- `id`: Unique identifier
- `property_id`: Reference to Property
- `user_id`: Reference to User (the guest)
- `start_date`
- `end_date`
- `status`: confirmed, pending, cancelled

**Relationships:**
- A booking is made by one user (the guest).
- A booking is for one property.
- A booking may result in one payment.
- 
### 4. Review

**Important Fields:**
- `id`: Unique identifier
- `property_id`: Reference to Property
- `user_id`: Reference to User (the reviewer)
- `rating`: e.g., 1–5 stars
- `comment`

**Relationships:**
- A review is written by one user for one property.
- A property can have many reviews.
- A user can write many reviews.
### 5. Payment

**Important Fields:**
- `id`: Unique identifier
- `booking_id`: Reference to Booking
- `amount`
- `payment_date`
- `status`: paid, pending, failed

**Relationships:**
- A payment is linked to one booking.
- A payment is made by the guest (user) and received by the host (user, through the booking/property relationship).
## Feature Breakdown
## API Security Overview
## CI/CD Pipeline Overview
