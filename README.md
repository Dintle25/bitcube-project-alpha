## RoomBooking - Conference Room Booking System

## Project Overview
The Conference Room Booking System is a web application designed to help office teams efficiently book, manage, and track the usage of conference rooms.

It solves common problems such as double bookings, difficulty finding suitable rooms, and poor visibility of room availability.

## Target Users:

Employees
Receptionists
Facilities Managers
Administrators

## Prerequisites
- Docker installed on your computer

## Steps

```bash
# 1. Clone the repository
git clone <repo-url>
cd assignment_3.3

# 2. Build the Docker image
docker build -t room-bookiing:latest .

# 3. Run the container
docker run -d -p 8080:80 --name room-booking -e APP_ENV=production -e VERSION=1.0.0 room-booking:latest
