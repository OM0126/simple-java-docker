# Simple Java Docker

A simple Java application containerized using Docker and deployed on an AWS EC2 Ubuntu instance.

## Project Overview

This project demonstrates how to:

* Launch an AWS EC2 Ubuntu instance
* Connect to the EC2 instance using SSH
* Install Docker
* Clone the project from GitHub
* Build a Docker image
* Run a Docker container
* Verify Docker images and containers
* Push the project to GitHub.

---

## Tech Stack

* Java
* Docker
* Ubuntu 22.04
* AWS EC2
* Git
* GitHub.

---

## Project Structure

```text
simple-java-docker/
├── Dockerfile
├── README.md
└── src
    └── Main.java
```

---

## Step 1: Launch an EC2 Instance

* Launch an Ubuntu EC2 instance.
* Choose the `t2.micro` instance type.
* Create or select an existing key pair.
* Allow SSH (Port 22) in the Security Group.
* Launch the instance.

---

## Step 2: Connect to EC2

```bash
chmod 400 my-key.pem
```

```bash
ssh -i my-key.pem ubuntu@<EC2-PUBLIC-IP>
```

---

## Step 3: Update the System

```bash
sudo apt update
sudo apt upgrade -y
```

---

## Step 4: Install Docker

```bash
sudo apt install docker.io -y
```

Start Docker:

```bash
sudo systemctl start docker
```

Enable Docker:

```bash
sudo systemctl enable docker
```

Verify installation:

```bash
docker --version
```

---

## Step 5: Clone the Repository

```bash
git clone https://github.com/OM0126/simple-java-docker.git
```

```bash
cd simple-java-docker
```

---

## Step 6: Dockerfile

```dockerfile
FROM eclipse-temurin:17-jdk-alpine

WORKDIR /app

COPY src/Main.java .

RUN javac Main.java

CMD ["java", "Main"]
```

---

## Step 7: Build the Docker Image

```bash
sudo docker build -t java-app .
```

Verify:

```bash
sudo docker images
```

---

## Step 8: Run the Docker Container

```bash
sudo docker run java-app
```

Expected Output:

```text
Hello, Docker! Current date: <current date and time>
```

---

## Useful Docker Commands

Build Image

```bash
sudo docker build -t java-app .
```

Run Container

```bash
sudo docker run java-app
```

List Images

```bash
sudo docker images
```

List Running Containers

```bash
sudo docker ps
```

List All Containers

```bash
sudo docker ps -a
```

Stop a Container

```bash
sudo docker stop <container-id>
```

Remove a Container

```bash
sudo docker rm <container-id>
```

Remove an Image

```bash
sudo docker rmi <image-id>
```

---

## Git Commands

## Git Commands

### Initialize Git Repository

```bash
git init
```

### Check Repository Status

```bash
git status
```

### Add All Files

```bash
git add .
```

### Commit Changes

```bash
git commit -m "Initial commit"
```

### Rename Current Branch to Main

```bash
git branch -M main
```

### Add Remote Repository

```bash
git remote add origin https://github.com/<username>/<repository-name>.git
```

### Check Configured Remote

```bash
git remote -v
```

### Change Existing Remote URL

```bash
git remote set-url origin https://github.com/<username>/<repository-name>.git
```

### Push Code to GitHub

```bash
git push -u origin main
```

### Pull Latest Changes

```bash
git pull origin main
```

### Clone Repository

```bash
git clone https://github.com/<username>/<repository-name>.git
```


---

## Learning Outcomes

After completing this project, you will learn:

* AWS EC2 basics
* Connecting to a Linux server using SSH
* Installing Docker on Ubuntu
* Writing a Dockerfile
* Building Docker images
* Running Docker containers
* Basic Git and GitHub workflow
* Containerizing a Java application

---

## Author

**Om **
