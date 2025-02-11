# Running an HTML File Using Docker

This guide explains how to containerize a simple HTML page using Docker and Nginx.

---

## 1. Create an HTML File

First, create a simple `index.html` file inside a new directory (e.g., `docker-html`).

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Dockerized Web Page</title>
</head>
<body>
    <h1>Welcome to my Dockerized HTML Page!</h1>
</body>
</html>
```

Save this file inside the `docker-html` directory.

---

## 2. Create a Dockerfile

Inside the same `docker-html` directory, create a `Dockerfile`:

```dockerfile
# Use an official Nginx image
FROM nginx:latest  

# Copy HTML file to Nginx default directory
COPY index.html /usr/share/nginx/html/

# Expose port 80
EXPOSE 80
```

---

## 3. Build the Docker Image

Navigate to the `docker-html` directory and build the Docker image:

```sh
docker build -t my-html-site .
```

### Explanation:
- Creates a Docker image named `my-html-site`.
- Copies the `index.html` file into the Nginx web server’s default directory.

---

## 4. Run the Container

Once the image is built, run a container using:

```sh
docker run -d -p 8080:80 --name my-html-container my-html-site
```

### Explanation:
- `-d` runs the container in detached mode (in the background).
- `-p 8080:80` maps port `80` in the container to port `8080` on your machine.
- `--name my-html-container` assigns a name to the container.
- `my-html-site` is the name of the image.

---

## 5. Access the HTML Page

Open your browser and visit:

```
http://localhost:8080
```

You should see your HTML page displayed!

---

## 6. Stop and Remove the Container

To stop the container:

```sh
docker stop my-html-container
```

To remove it:

```sh
docker rm my-html-container
```

To remove the image:

```sh
docker rmi my-html-site