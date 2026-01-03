# Vehicle Rental System – Database Overview

## Overview
The Vehicle Rental System is a simple relational database designed to manage vehicle rentals efficiently.  
It supports user management, vehicle inventory tracking, and booking operations.  
This database structure is suitable for academic projects and beginner-to-intermediate SQL practice.

---

## Purpose
The main purpose of this system is to:
- Manage users such as admins and customers
- Store and track rental vehicles
- Handle vehicle booking records
- Practice relational database concepts and SQL logic

---

## System Components

### Users
The system includes users with two roles:
- **Admin** – manages vehicles and bookings
- **Customer** – rents vehicles

Each user has basic information such as name, email, phone number, and role.

---

### Vehicles
Vehicles represent the items available for rent.  
Each vehicle includes:
- Name and model
- Vehicle type (car, bike, truck, SUV)
- Registration number
- Daily rental price
- Availability status (available, rented, maintenance)

This helps track which vehicles can be rented at any time.

---

### Bookings
Bookings store rental transaction details.  
Each booking connects:
- A customer
- A vehicle
- Rental start and end dates
- Total rental cost
- Booking status (pending, confirmed, completed, cancelled)

This structure ensures clear tracking of rental history.

---

## Functional Capabilities
Using this database, you can:
- View booking details along with customer and vehicle information
- Identify vehicles that have never been rented
- Find available vehicles by type
- Analyze popular vehicles based on booking count

---

## Key Concepts Demonstrated
- Relational database design
- Primary and foreign key relationships
- Data validation using constraints
- Business logic through structured queries
- Basic reporting and data analysis

---

## Use Case
This project is ideal for:
- SQL assignments
- Database design practice
- Learning how rental systems work internally
- Backend foundation for a vehicle rental application
