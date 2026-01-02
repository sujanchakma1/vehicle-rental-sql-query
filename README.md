Vehicle Rental System – SQL Database
Overview

This project demonstrates a vehicle rental system database with users, vehicles, and bookings. It includes practical SQL queries to retrieve, filter, and analyze booking and vehicle data.

Database Schema
Users Table
create table users (
  user_id serial primary key,
  name varchar(100) not null,
  email varchar(100) unique not null,
  password text not null,
  phone_number text not null,
  role text not null check (role in ('admin', 'customer'))
);

Vehicles Table
create table vehicles (
  vehicle_id serial primary key,
  vehicle_name varchar(100) not null,
  type text not null check (type in ('car', 'bike', 'truck', 'SUV')),
  model text not null,
  registration_number text not null,
  daily_rent_price int not null check (daily_rent_price > 0),
  availability_status text not null check (availability_status in ('available', 'rented', 'maintenance'))
);

Bookings Table
create table bookings (
  booking_id serial primary key,
  customer_id int references users(user_id),
  vehicle_id int references vehicles(vehicle_id),
  rent_start_date date not null,
  rent_end_date date not null check (rent_end_date > rent_start_date),
  total_price numeric not null check (total_price > 0),
  status text not null check (status in ('pending', 'confirmed', 'completed', 'cancelled'))
);

Example Queries
1. Join Bookings with Users and Vehicles
select
  b.booking_id,
  u.name as customer_name,
  v.vehicle_name,
  b.rent_start_date,
  b.rent_end_date,
  b.status
from bookings b
inner join users u on b.customer_id = u.user_id
inner join vehicles v on b.vehicle_id = v.vehicle_id;

2. Find All Available Vehicles
select *
from vehicles
where availability_status != 'rented';

3. Find Available Cars
select *
from vehicles
where type = 'car'
  and availability_status = 'available';

4. Vehicles with More Than 2 Bookings
select
  vehicle_name,
  count(b.booking_id) as total_bookings
from vehicles v
inner join bookings b on v.vehicle_id = b.vehicle_id
group by vehicle_name
having count(b.booking_id) > 2;

Summary

Tables are connected using foreign keys.

Data validation is enforced with CHECK, NOT NULL, and UNIQUE constraints.

Queries demonstrate JOINs, filtering, and aggregation in SQL.