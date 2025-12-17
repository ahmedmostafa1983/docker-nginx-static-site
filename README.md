# Static HTML Website Deployment Using Nginx and Docker

##  Project Overview

This project demonstrates how to deploy a **simple static HTML website** using **Nginx** inside a **Docker container**.

The website files are mounted from the host machine into the container using a **bind mount**, allowing instant updates without restarting or rebuilding the container.

---

##  Project Objectives

* Create a directory on the host machine to store website files
* Create a simple `index.html` page
* Run an Nginx container
* Expose the container on port `8080`
* Access the website from a web browser
* Observe live updates using Docker volumes

---

##  Technologies Used

* HTML
* Nginx
* Docker

---

##  Project Structure

```
website/
└── index.html
```

---

##  How to Run the Project

###  Create project directory

```bash
mkdir website
cd website
```

###  Create `index.html`

Add a simple HTML page inside the directory.

###  Run the Nginx container

```bash
docker run -d \
  --name web \
  -p 8080:80 \
  -v $(pwd):/usr/share/nginx/html \
  nginx
```

---

##  Access the Application

Open your browser and go to:

```
http://localhost:8080
```

---

##  Live Update Explanation

Since the website directory is mounted into the container using a **bind mount volume**, any change made to `index.html` on the host machine is reflected immediately in the browser without restarting the container.

This setup is ideal for development and testing environments.

---

##  Key Learning Outcomes

* Running containers using Docker CLI
* Serving static content with Nginx
* Using bind mounts to sync files between host and container
* Understanding how Docker volumes enable live updates

---

##  Author

Ahmed Mostafa Abbas
