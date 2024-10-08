# Static Web App Containerization with Nginx

This project demonstrates how to containerize a simple static web application (HTML, CSS, and JavaScript) using Nginx in a Docker container.

## Table of Contents
- [Prerequisites](#prerequisites)
- [Project Structure](#project-structure)
- [Docker Setup](#docker-setup)
- [Nginx Configuration](#nginx-configuration)
- [Building and Running the Container](#building-and-running-the-container)
- [Accessing the Web App](#accessing-the-web-app)
- [Stopping the Container](#stopping-the-container)

## Prerequisites

Before starting, ensure you have the following installed:
- [Docker](https://www.docker.com/get-started) (version 20.10 or higher)
- Basic knowledge of HTML, CSS, JavaScript, and Docker

```
# Stage 1: Build stage
FROM nginx:alpine

# Copy the Nginx configuration file
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf

# Copy the static web app files
COPY ./public /usr/share/nginx/html

# Expose port 80 to access the application
EXPOSE 80

# Start Nginx when the container starts
CMD ["nginx", "-g", "daemon off;"]

```
this should be the dockerfile content
---

