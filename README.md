# airbnb-clone-project
The Airbnb Clone Project is a comprehensive, real-world application designed to simulate the development of a robust booking platform like Airbnb. It involves a deep dive into full-stack development, focusing on backend systems, database design, API development, and application security.

## 🎯 Learning Objective

This project is tailored to enhance expertise in modern software development practices. By completing these tasks, learners will:

*   **Master Collaborative Workflows:** Utilize GitHub for effective team collaboration, including issue tracking, branching strategies, and code reviews.
*   **Architect Robust Backends:** Deepen understanding of backend architecture and database design principles for scalable applications.
*   **Implement Advanced Security:** Integrate advanced security measures to protect user data and secure API endpoints.
*   **Manage CI/CD Pipelines:** Gain proficiency in designing and managing Continuous Integration and Continuous Deployment pipelines for efficient and reliable deployment.
*   **Plan & Document Effectively:** Strengthen the ability to document and plan complex software projects from conception to deployment.
*   **Integrate Modern Technologies:** Develop a strong understanding of integrating Django, MySQL, and GraphQL into a unified and efficient development ecosystem.

## 🛠️ Technology Stack

*   **Backend Framework:** Django / Django REST Framework
*   **Database:** MySQL
*   **API Query Language:** GraphQL
*   **Version Control:** GitHub (with Issues, Projects, and Actions for CI/CD)
*   **Deployment:** (To be determined, e.g., AWS, Heroku, Docker)

## 👥Team Roles & Responsibilities

This project leverages a modern, agile team structure to ensure both technical excellence and alignment with business goals.

## ROLE: Product Owner (PO)	
**KEY FOCUS: *Vision & Value***	
**Primary Responsibilities**
Defines the product vision, manages the backlog, and is the ultimate decision-maker for what features provide maximum business value.
Business Analyst (BA)	Requirements & Translation	Bridges the gap between stakeholder needs and technical execution, translating abstract ideas into clear, tangible requirements for the team.

## ROLE: Project Manager (PM)
**KEY FOCUS: *Process & Delivery***
**Primary Responsibilities**
		Facilitates communication, maintains transparency, and ensures the project is delivered on time and within budget by managing processes and motivating the team.
UI/UX Designer	User Experience & Design	Creates intuitive, user-friendly designs and maps user journeys to ensure the product is functional, engaging, and achieves business goals.

## ROLE: Software Architect	
**KEY FOCUS: *System Design & Standards***	
**Primary Responsibilities**
	Designs the high-level application architecture, selects tools and technologies, and sets coding standards to ensure the product is secure, stable, and scalable.
Software Developer	Implementation & Problem-Solving	Writes the code for the application. Includes Front-end (client-side), Back-end (server-side, APIs, logic), and Full-stack developers.

## ROLE:QA Engineer	 	
**KEY FOCUS: *Quality & Validation***	
**Primary Responsibilities**
	Verifies the application meets all functional and non-functional requirements through manual testing, bug reporting, and quality analysis.

## ROLE: Test Automation Engineer
**KEY FOCUS:*Efficiency & Coverage***	
**Primary Responsibilities**
		Designs and writes automated test scripts to enable fast, reliable, and continuous feedback on application quality.

## ROLE: DevOps Engineer	
**KEY FOCUS: *Integration & Delivery***	
**Primary Responsibilities**
	Builds and maintains CI/CD pipelines to automate the software delivery process, enabling frequent and stable releases.

## DATABASE DESIGN
The database is a relational model built with PostgreSQL, designed to manage users, property listings, bookings, reviews, and payments efficiently.

**Key Entities & Relationships**
**Users**

* id (Primary Key)

* username

* email

* password_hash

* phone_number

**Relationships:** A User can have multiple Properties (as a Host) and multiple Bookings (as a Guest).

**Properties**

* id (Primary Key)

* title

* description

* price_per_night

* host_id (Foreign Key to Users)

**Relationships:** A Property belongs to one User (the host). A Property can have many Bookings and many Reviews.

**Bookings**

* id (Primary Key)

* check_in_date

* check_out_date

* total_price

* guest_id (Foreign Key to Users)

* property_id (Foreign Key to Properties)

**Relationships:** A Booking belongs to one User (the guest) and one Property.

**Reviews**

* id (Primary Key)

* rating

* comment

* booking_id (Foreign Key to Bookings)

* guest_id (Foreign Key to Users)

**Relationships:** A Review is created for one Booking, written by the User (guest) who made that booking.

**Payments**

* id (Primary Key)

* amount

* status (e.g., pending, completed, failed)

* booking_id (Foreign Key to Bookings)

* payment_intent_id (from Stripe/Paypal)

* Relationships: A Payment is associated with one Booking.