# Dockerized Node.js Application

## Overview

This project demonstrates how to containerize a simple Node.js "Hello World" application using Docker and push the image to Docker Hub.

---

## Application

A basic Express server that returns:

**Hello World from Docker CI/CD**

---


## Steps Taken

### 1. Create Application

* Created a simple Node.js application using Express
* Configured the app to run on port 5000

---

### 2. Build Docker Image

```bash
docker build -t ci-cd-app .
```

---

### 3. Run Docker Container

```bash
docker run -p 5000:5000 ci-cd-app
```

Open in browser:

```
http://localhost:5000
```

---

### 4. Push Image to Docker Hub

#### Tag the Image

```bash
docker tag ci-cd-app kingkabari/ci-cd-app
```

#### Push the Image

```bash
docker push kingkabari/ci-cd-app
```

---

## Dockerfile Explanation

* **FROM node:18-alpine**
  Uses a lightweight Node.js base image

* **WORKDIR /app**
  Sets the working directory inside the container

* **COPY package*.json ./**
  Copies dependency files

* **RUN npm install**
  Installs required dependencies

* **COPY . .**
  Copies application source code

* **EXPOSE 5000**
  Opens port 5000

* **CMD ["node", "index.js"]**
  Starts the application

---

## Docker Hub Repository

https://hub.docker.com/r/kingkabari/ci-cd-app
