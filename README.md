# Airbnb Clone

 Airbnb Clone project is designed to provide a robust and scalable foundation for managing user interactions, property listings, bookings, and payments. It'll support various functionalities required to **mimic the core features** of Airbnb. 

 ## Project Goals:
 * **User Management**: Implement a secure system for user registration, authentication, and profile management.
 * **Property Management**: Develop features for property listing creation, updates, and retrieval.
* **Booking System**: Create a booking mechanism for users to reserve properties and manage booking details.
* **Payment Processing**: Integrate a payment system to handle transactions and record payment details.
* **Review System**: Allow users to leave reviews and ratings for properties.
* **Data Optimization**: Ensure efficient data retrieval and storage through database optimizations.


 ## Technology Stack:
* **Django**: A high-level Python web framework used for building the RESTful API.
* **Django REST Framework**: Provides tools for creating and managing RESTful APIs.
* **PostgreSQL**: A powerful relational database used for data storage.
* **GraphQL**: Allows for flexible and efficient querying of data.
* **Celery**: For handling asynchronous tasks such as sending notifications or processing payments.
* **Redis**: Used for caching and session management.
* **Docker**: Containerization tool for consistent development and deployment environments.
* **CI/CD Pipelines**: Automated pipelines for testing and deploying code changes.

## Team Roles:
* **Backend Developer**: Responsible for implementing the core of an app- its algorithms, API endpoints, database schemas, and business logic.
* **Database Administrator**: Manages database design, indexing, and optimizations.
* **DevOps Engineer**: Builds Continuous Integration and Continuous Delivery (CI/CD) pipelines for faster delivery. Also handles deployment, monitoring, and scaling of the backend services.
* **QA Engineer**: Ensures the backend functionalities are thoroughly tested and meet quality standards, and application performs according to requirements.

## Database Design:
Outline of the entities of the system and how they relate to one another.

### **Users**:
Individuals using the platform, including guests and hosts.

**"Users'" Fields:**
* `id` - Primary Key
* `name`
* `email`
* `role` (e.g host, guest, admin)

**Relationships:**
* A **user** can list **multiple properties** (if host).
* A **user** can make **multiple bookings** (if guest).
* A **user** can leave **multiple reviews**.


### **Properties**:
Represents the accommodations listed by hosts.

**"Properties'" Fields:**
- `id`- Primary Key
- `description`
- `location`
- `pricePerNight`
- `hostId` (Foreign Key → Users.id)

**Relationships:**
- A **property** is owned by one **user** (host).
- A **property** can have many **bookings**.
- A **property** can have many **reviews**.


### **Bookings**:
Captures reservation details for properties.

**"Bookings'" Fields:**
- `id`- Primary Key
- `propertyId` (Foreign Key → Properties.id)
- `userId` (Foreign Key → Users.id)
- `date`
- `totalPrice`

**Relationships:**
- A **booking** is made by a **user**.
- A **booking** is for one **property**.
- A **booking** can have one **payment**.


### **Reviews**:
User feedback on experience and properties.

**"Reviews'" Fields:**
- `id`- Primary Key
- `propertyId` (Foreign Key → Properties.id)
- `userId` (Foreign Key → Users.id)
- `rating` (1–5)
- `comment`

**Relationships:**
- A **review** is written by a **user**.
- A **review** belongs to one **property**.


### **Payments**:
Tracks payment transactions for bookings.

**"Payments'" Fields:**
- `id`- Primary Key
- `bookingId` (Foreign Key → Bookings.id)
- `amount`
- `paymentMethod`
- `paymentDate`

**Relationships:**
- A **payment** belongs to one **booking**.


## Feature Breakdown:
* User Management: Implement a secure system for user registration, authentication, and profile management. This enables users to create and manage their accounts on the app.
* Property Management: Develop features for property listing creation, updates, and retrieval. With this feature, potential guests can view properties listed on the sites by hosts.
* Booking System: Create a booking mechanism for users to reserve properties and manage booking details. Users, therefore, can rest assured that booked properties stay reserved for them.
* Payment Processing: Integrate a payment system to handle transactions and record payment details. This helps users to book properties conveniently.
* Review System: Allow users to leave reviews and ratings for properties. This enables potential users to make better informed decisions.
* Data Optimization: Ensure efficient data retrieval and storage through database optimizations. This improves user experience, reducing load times.

## API Security:



## CI/CD Pipelines:
These are automated series of steps that streamline the software development life cycle through automation of processes/stages such as code testing, building, packaging, and deployment. For this project, automated testing helps in identifying and fixing bugs early, improving software quality and stablity. Pipelines also foster better collaboration between development,testing, and operations teams. 

Some tools that could be used to build CI?CD pipelines include;
* Jenkins
* GitHub Actions
* CircleCI
* Azure DevOps
* GitLab CI
