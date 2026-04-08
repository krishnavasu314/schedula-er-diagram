# 🏥 Schedula – ER Diagram Design

## 📌 Overview

This project presents the **Entity-Relationship (ER) Diagram** for a healthcare appointment system based on the Schedula wireframes.

The system is designed to manage the complete lifecycle of a patient’s interaction with a doctor, including:

* Doctor discovery
* Appointment booking
* Patient (family) management
* Payments
* Medical records
* Chat communication
* Notifications
* Feedback & support

---

## 🎯 Objective

The goal of this design is to create a **scalable, modular, and real-world aligned database structure** that supports healthcare workflows efficiently.

---

## 🧠 Core Concept

At the center of the system is the **Appointment** entity.

It acts as the **transactional hub**, connecting all major components:

* User (who books)
* Patient (who receives treatment)
* Doctor (who provides consultation)
* Payment
* Medical Record
* Chat
* Feedback
* Notifications

This ensures that all interactions are organized around a single consultation event.

---

## 🏗️ Entities & Relationships

### 👤 User

Represents the account holder using the application.

* A user can manage multiple patients
* A user can book multiple appointments

---

### 🧍 Patient

Represents the person receiving treatment.

* Linked to User (family support)
* One user → many patients

---

### 👨‍⚕️ Doctor

Represents healthcare professionals.

* Includes specialization, experience, and qualifications
* Linked to Clinic

---

### 🏥 Clinic

Represents the hospital or location.

* One clinic → many doctors

---

### 🕒 Doctor Availability

Defines when a doctor is available.

* Stores day and time ranges
* One doctor → many availability slots

---

### 📅 Appointment (Core Entity)

Represents a booking between a patient and doctor.

Includes:

* User
* Patient
* Doctor
* Date & time
* Status (Booked, Cancelled, Completed)
* Token number
* Consultation type

---

### 💳 Payment

Handles financial transactions.

* One appointment → one payment
* Supports refunds and tracking

---

### 📋 Medical Record

Stores consultation details.

* Complaint, diagnosis, notes
* One appointment → one record

---

### 💬 ChatMessage

Supports communication between doctor and patient.

* One appointment → many messages

---

### ⭐ Feedback

Stores user ratings after consultation.

* Doctor rating
* Clinic rating
* Waiting time
* Comments

---

### 🔔 Notification

Handles reminders and alerts.

* Linked to user and appointment

---

### 🛠️ SupportTicket

Handles user issues and queries.

* One user → many tickets

---

## 🔗 Relationship Summary

* User → Patient (1:N)
* User → Appointment (1:N)
* Patient → Appointment (1:N)
* Doctor → Appointment (1:N)

Each Appointment:

* → Payment (1:1)
* → Feedback (1:1)
* → Medical Record (1:1)
* → ChatMessage (1:N)

---

## 🧠 Design Decisions

* ✅ Separated User and Patient for family-based booking
* ✅ Appointment as central entity for all workflows
* ✅ DoctorAvailability for flexible scheduling
* ✅ Normalized schema to reduce redundancy
* ✅ Context-based linking for chat and records


---

## 🎥 Loom Video Explanation

https://www.loom.com/share/8d486bbd9eb74d1d9c33658f9de2e7c1

---

## 📌 Conclusion

This ER design closely reflects real-world healthcare workflows while ensuring scalability, modularity, and maintainability. It provides a strong foundation for building a production-ready healthcare system.
