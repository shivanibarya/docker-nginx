# Docker NGINX Project
NGINX Docker Project Documentation

1️⃣ Project Overview
This project demonstrates:
•	Running NGINX in Docker
•	Creating a custom Docker image
•	Pushing the image to Docker Hub
•	Version-controlling the project using GitHub
•	Accessing NGINX in a web browser
2️⃣ Prerequisites
•	Docker installed on your system
•	Git installed
•	Docker Hub account (shivanibarya)
•	GitHub account (shivanibarya)
•	Basic knowledge of Linux commands
3️⃣ Project Structure
docker-nginx/
├─ Dockerfile
├─ index.html
├─ README.md
└─ other project files (optional)
4️⃣ index.html
Create a file named index.html inside your project folder with the following content:
 
<h1>Hello from Custom NGINX Docker</h1>
<p>Welcome to Shivani's Docker NGINX Project!</p>

5️⃣ Dockerfile
Create a file named Dockerfile inside your project folder with the following content:
# Use latest official NGINX image
FROM nginx:latest
 
# Copy the custom index.html into the NGINX default web folder
COPY index.html /usr/share/nginx/html/index.html
# Expose HTTP port
EXPOSE 80
# Start NGINX in foreground
CMD ["nginx", "-g", "daemon off;"]

6️⃣ Docker Steps
Step 1: Build Docker Image
docker build -t shivani-nginx .
Check image:
docker images
Step 2: Run Container (Detached Mode)
docker run -d --name shivani-nginx-container -p 8080:80 shivani-nginx
Check running container:
docker ps
 
Step 3: Access NGINX in Browser
•	Local: http://localhost:8080
•	EC2/Public server: http://<EC2-public-IP>:8080
 
Step 4: Login to Docker Hub
docker login
•	Username: shivanibarya
•	Password: Docker Hub password or Personal Access Token (PAT)
Step 5: Tag Docker Image for Docker Hub
docker tag shivani-nginx shivanibarya/nginx-project:latest
Step 6: Push Image to Docker Hub
docker push shivanibarya/nginx-project:latest
 
Verify on Docker Hub repository.
 
7️⃣ GitHub Version Control
Step 1: Initialize Git
git init
Step 2: Add project files
git add .
Step 3: Commit changes
git commit -m "Docker NGINX project"
Step 4: Add remote repository
git remote add origin https://github.com/shivanibarya/docker-nginx.git
If remote exists:
git remote set-url origin https://github.com/shivanibarya/docker-nginx.git
Step 5: Push to GitHub
git branch -M main
git push -u origin main
Use GitHub Personal Access Token (PAT) as password.
 
8️⃣ Accessing NGINX in Browser
1.	If running locally, open: http://localhost:8080
 
2.	If running on EC2/public server, open: http://<EC2-public-IP>:8080
3.	Make sure port 8080 is allowed in your firewall or EC2 security group.
4.	Refresh the page after restarting container to see updates.

9️⃣ Updating Content
•	Modify index.html or Dockerfile as needed.
•	Rebuild image:
docker build -t shivani-nginx .
•	Restart container:
•	docker stop shivani-nginx-container
•	docker rm shivani-nginx-container
•	docker run -d --name shivani-nginx-container -p 8080:80 shivani-nginx

10  Summary Flow
1.	Write index.html
2.	Write Dockerfile
3.	Build image: docker build -t shivani-nginx .
4.	Run container: docker run -d -p 8080:80 shivani-nginx
5.	Test in browser
6.	Push image to Docker Hub
7.	Initialize Git → Commit → Push to GitHub

11️⃣ References
•	Docker Official Docs
•	NGINX Official Docs
•	GitHub Docs
•	Docker Hub



