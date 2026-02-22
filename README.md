# Dockerized Node.js Application with CI/CD Deployment

This repository contains a **Dockerized Node.js application** (GraphQL + REST API) with an automated **CI/CD pipeline** that builds, publishes, and deploys the application to an **AWS EC2 instance** using **GitHub Actions** and **Docker**.

---

## 🚀 Project Overview

This project demonstrates:

- 🐳 Containerization of a Node.js backend using **Docker**.
- 🤖 Automated CI/CD pipeline using **GitHub Actions** to build Docker images and push them to **Docker Hub**.
- 🛠 Self‑hosted GitHub Actions runner configured on **AWS EC2** for deployment.
- ☁️ Deployment automation to an **EC2 instance**, pulling and running the latest Docker image.
- 🔒 Secure authentication using **GitHub Secrets** and **SSH keys**.
- 📡 Exposed API endpoints for **GraphQL** and **REST**.

---

## 📦 Features

### Application

- **GraphQL API** with queries and mutations.
- **REST endpoint** to fetch user data from a sample JSON file.
- Self‑contained backend that can run independently via **Docker**.

### CI/CD Workflow

- **Build:** Build Docker image using GitHub Actions.
- **Publish:** Push image to Docker Hub (`vivek456vk/nodejs-app:latest`).
- **Deploy:** Pull image on AWS EC2 runner, remove the previous container, and start a new one.

---

## 📂 Repo Structure

```
dockerized-nodejs-application-deployment/
├── .github/workflows/
│ └── cicd-workflow.yml        # CI/CD automation
├── Dockerfile                 # Docker container definition
├── .dockerignore              # Ignore files during Docker build
├── server.js                  # Node.js application
├── package.json               # NPM dependencies and scripts
├── package-lock.json
├── MOCK_DATA.json             # Sample data used by API
├── .gitignore
└── README.md
```

---

## ⚙️ How It Works

1. **GitHub Actions** triggers on every commit to the `main` branch.
2. The workflow builds a Docker image of your Node.js application.
3. After logging in securely to **Docker Hub** using secrets, it pushes the image.
4. Using a **self‑hosted GitHub runner on AWS EC2**, the deploy job:
   - pulls the latest image,
   - removes any old container,
   - runs the updated container on port **5000**.

---

## ☁️ Deployment (GitHub Actions)

The CI/CD workflow automatically handles:

- Building and pushing the Docker image to Docker Hub.

- Deploying the application directly on your self-hosted EC2 runner.

- Pulling the latest Docker image and running the container automatically.

**Secrets required in GitHub:**

- `DOCKER_USERNAME`

- `DOCKER_PASSWORD`

---

## 📌 Tech Stack & APIs

- Node.js

- Express

- GraphQL API – queries and mutations for user data

- REST API – endpoint `/rest/getAllUsers` for fetching all users

- Docker

- GitHub Actions

- AWS EC2 (self-hosted runner)

- Docker Hub

- Linux (EC2 Instance)

---

## 💡 Conclusion

This project demonstrates a complete **DevOps workflow** for a **Dockerized Node.js backend**, automated CI/CD deployment via GitHub Actions, and direct deployment on a cloud-hosted self-hosted runner. It’s a strong showcase of hands-on **cloud and DevOps skills**.
