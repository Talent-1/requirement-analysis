# Requirement Analysis in Software Development 
This repsitory is created to document and demonstrate the process of requirement analysis in software developement. It will include key concepts, and practical exercises relating to identifying, analyzing, and documenting software requirements.

---

## What is Requirement Analysis?
_Requirement Analysis_ is the process of identifying, understanding, and documenting what a software or web application must do --- including the needs, goals and expectations of it's users and stakeholders. It helps define _what to build_ before actual development begins.

---

## Why is Requirement Analysis Important?
Requirement Analysis is crucial in Software Development Life cycle because it;
- **Defines project goals clearly** – ensures developers know exactly what to build.
- **Prevents misunderstandings** – reduces confusion between clients and developers.
- **Saves time and cost** – avoids rework caused by unclear or changing requirements.
- **Guides design and development** – serves as a blueprint for the next SDLC phases.
- **Ensures user satisfaction** – aligns the final product with user needs and expectations.

---

## Key Activities in Requirement Analysis.
- **Requirement Gathering:**
The process of collecting all possible needs and expectations from stakeholders (users, clients, managers, etc.) for the system.
- **Requirement Elicitation:**
Involves using techniques like interviews, surveys, or observation to draw out detailed and accurate requirements from stakeholders.
- **Requirement Documentation:**
Writing down the gathered and elicited requirements clearly in a structured format, often in a _Software Requirements Specification (SRS)_ document.
- **Requirement Analysis and Modeling:**
Examining and organizing requirements to understand relationships, resolve conflicts, and represent them visually using models (like use-case diagrams or data flow diagrams).
- **Requirement Validation:**
Ensuring that the documented requirements are correct, complete, and meet user needs before development begins.

---

## Types of Requirements.
There are two types of requirements; 

###  Functional Requirements
_Functional Requirements_ are specific statements that describe **what a system should do** — the features, actions, or services it must perform to meet user needs.
They define the **behavior or functions** of the software in response to user interactions or inputs.

**✅ Examples of Functional Requirements:**
These describe the **core actions and features** the hotel booking system must perform. It includes;

- **User Registration & Login:**
Users (customers and hotel managers) must be able to create accounts and securely log in.
- **Hotel Listing Management:**
Hotel managers can add, edit, or delete hotel details such as room types, prices, images, and availability.
- **Search & Filter Hotels:**
Customers can search for hotels by location, date, price, amenities, and ratings.
- **Hotel Booking:**
Users can select rooms, confirm booking dates, and reserve rooms through the booking service.
- **Payment Processing:**
The system must integrate with third-party payment gateways to process online transactions securely.
- **View Bookings:**
Both customers and hotel managers can view current and past bookings through the “View Booking Service.”
- **Notifications:**
The system sends notifications to customers and managers for actions like successful bookings, payment confirmation, and new offers.
- **Data Synchronization:**
Updates made by hotel managers must be instantly reflected on the customer portal via APIs and messaging queues.
- **Content Delivery:**
A CDN (Content Delivery Network) ensures hotel data, images, and offers are served quickly to users across different locations.
- **Data Archival:**
Old booking data is automatically archived in Cassandra for long-term storage and analytics.

### ⚙️ Non-Functional Requirements
_Non-functional Requirements_ define **how a system performs** rather than **what it does**. They describe the system’s **quality attributes** such as speed, security, reliability, and usability.
These describe the quality and performance characteristics of the system.

**Examples of Non-functional Requirements:** 
From the booking App includes,
- **Performance:**
The system should handle thousands of concurrent users without delay.
Average API response time should be under 2 seconds.
- **Scalability:**
The system should scale horizontally by using microservice architecture to manage high traffic.
- **Availability:**
The platform should maintain 99.9% uptime to ensure 24/7 access.
-  **Reliability:**
Data replication via master-slave databases must ensure no data loss during failures.
- **Security:**
All user and payment data must be encrypted using SSL/TLS.
Only authenticated users should access restricted services.
- **Usability:**
The interface should be simple, responsive, and mobile-friendly for both hotel managers and customers.
- **Maintainability:**
Each microservice (e.g., hotel management, booking, notification) should be independently upgradable without affecting others.
- **Data Consistency:**
Updates from the master database should be instantly synchronized with slave databases and caches.
- **Fault Tolerance:**
The system should automatically recover from server failures using load balancers and distributed clusters.
- **Analytics Support:**
Data streamed into Hadoop should support business analytics and customer behavior tracking.

---

## 🧩 What is a Use Case Diagram?

A **Use Case Diagram** is a visual representation in **UML (Unified Modeling Language)** that shows the **interactions between users (actors)** and a **system’s functions (use cases)**.
It focuses on what the **system does** — not **how** it does it.

### 🎯 Benefits of Use Case Diagrams**

- **Clarifies system scope:**
Clearly shows what functionalities are part of the system and who interacts with them.
- **Improves communication:**
Helps non-technical stakeholders (clients, users) understand the system easily.
- **Identifies user roles:**
Highlights different types of users and their interactions (e.g., customer vs. manager).
- **Simplifies requirement analysis:**
Links system functions directly to user requirements.
- **Supports documentation and testing:**
Provides a foundation for writing user stories, test cases, and validation steps.

![ Hotel Booking System  Diagram](https://drive.google.com/file/d/1C8qxTBG8z9InoddzoPBYHA_In3LKKCEZ/view?usp=drive_link)


[View the Hotel Booking system diagram on Draw.io](https://drive.google.com/file/d/1_W2LS0QyGE0zLDJ0YJkAsLYkSWRM8aWU/view?usp=sharing)


---

## 🧩 Importance of Acceptance Criteria in Requirement Analysis

Acceptance Criteria are the predefined conditions that a software feature must meet for it to be accepted by stakeholders or end-users.
They act as a bridge between requirements and testing, ensuring that both developers and clients have the same understanding of what “done” means.

**Key Importance:**

- **Clarity and Shared Understanding:**
Defines clear expectations between developers, testers, and stakeholders about what each feature should do.
- **Guides Development:**
Helps developers know the exact functionality to implement and the boundaries of the feature.
- **Supports Testing and Validation:**
Provides measurable conditions for QA teams to verify that the feature works as intended.
- **Reduces Miscommunication:**
Prevents ambiguity by specifying detailed acceptance conditions rather than vague goals.

- **Ensures Quality Delivery:**
Guarantees that every user story or feature meets the business and user needs before being approved.

**🛒 Example: Acceptance Criteria for the “Checkout” Feature in a Hotel Booking System**

**Feature: Checkout and Payment Processing**

- **User Story:**
As a customer, I want to complete my booking by securely paying for my hotel reservation, so that I can confirm my stay.

 **Acceptance Criteria:**

- The system must allow the user to review booking details before proceeding to payment.
- The user must be able to choose a payment method (credit/debit card, PayPal, or bank transfer).
- Payment information must be transmitted securely using HTTPS and encryption.
- The system should confirm payment through an integrated third-party payment gateway (e.g., Stripe, Paystack).
- Upon successful payment, the user must receive a **booking confirmation message** and an **email receipt**.
- If payment fails, the system should display an error message and prompt the user to retry or select another payment method.
- The booking status must automatically change to “Confirmed” after successful payment and “Pending” if payment fails.
