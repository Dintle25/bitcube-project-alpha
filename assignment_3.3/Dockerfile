# RoomBooking - Conference Room Booking System

# Base Image
FROM nginx:alpine

# Remove default nginx files
RUN rm -rf /usr/share/nginx/html/*

# Copy your own index.html
COPY roomBooking.html /usr/share/nginx/html/index.html

# Expose port
EXPOSE 80