# API Usage Examples

This document provides practical examples of how to use the Conference Room Booking System API.

## 1. Authentication

### Login (Get JWT Token)


POST /auth/login
Content-Type: application/json

{
  "email": "employee@company.com",
  "password": "securepassword123"
}

response example: 
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "user": {
    "id": 25,
    "name": "Dintle Khumalo",
    "role": "employee",
    "department": "Engineering"
  }
}


## 2. Room Managment
to get all rooms
GET /rooms
Authorization: Bearer

find available rooms:
GET /rooms/available?startTime=2026-05-25T09:00:00Z&endTime=2026-05-25T10:00:00Z&capacity=6
Authorization: Bearer 

## 3. Bookings
POST /bookings
Authorization: Bearer
Content-Type: application/json

{
  "roomId": 101,
  "startTime": "2026-05-25T10:00:00Z",
  "endTime": "2026-05-25T11:00:00Z",
  "title": "Sprint Planning Meeting",
  "description": "Weekly team alignment"
}

get the booking:
GET /bookings
Authorization: Bearer 

delete the booking:
DELETE /bookings/452
Authorization: Bearer 


## 4. Availability
GET /rooms/101/availability?startTime=2026-05-25T10:00:00Z&endTime=2026-05-25T11:00:00Z
Authorization: Bearer 

response example:
{
  "available": false,
  "conflicts": [
    {
      "bookingId": 387,
      "title": "Client Meeting",
      "startTime": "2026-05-25T10:30:00Z"
    }
  ]
}

error handling: 
{
  "error": "Room already booked",
  "message": "The selected time slot is no longer available",
  "code": 409
}

