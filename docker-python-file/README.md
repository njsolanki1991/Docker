# Running Python File Using Docker

This guide explains how to containerize a simple python file using Docker and Nginx.

---

## 1. Create a Python File

First, create a simple `app.py` file inside a new directory (e.g., `docker-python-file`).
```sh
print("Hello from Dockerized Python!")
```

Save this file inside the `docker-python-file` directory.

---

## 2. Create a Dockerfile

Inside the same `docker-html` directory, create a `Dockerfile`:

```dockerfile
# Use the official Python image
FROM python:3.9-slim

# Copy the Python script to the container
COPY app.py .

# Run the script when the container starts
CMD ["python", "app.py"]
```

---

## 3. Build the Docker Image

Navigate to the `docker-python-file` directory and build the Docker image:

```sh
docker build -t my-python-image .
```

### Explanation:
- Creates a Docker image named `my-python-image`.

---

## 4. Run the Container

Once the image is built, run a container using:

```sh
docker run --name my-python-container my-python-image
```

---

## 5. Stop and Remove the Container

To stop the container:

```sh
docker stop my-python-container
```

To remove it:

```sh
docker rm my-python-container
```

To remove the image:

```sh
docker rmi my-python-image
