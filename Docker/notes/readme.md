## Chapter 1: Introduction to containers and Docker

### What are containers?

Containers are lightweight, portable, and isolated environments that allow developers to package applications and their dependencies together. This ensures that the application runs consistently across different computing environments, whether it's on a developer's local machine, a testing server, or in production.

![image](https://github.com/user-attachments/assets/10eebf5e-44b7-4f03-a402-00e9755ab01b)

Containers bundle an application with all its dependencies into a single portable unit ensuring that the application runs consistently across different environments. It provides isolation and improves resource efficiency.

Benefits of containers:

- Isolation: Each container runs in isolation from others, meaning it has its own file system, libraries, dependencies, and environment. This allows you to run multiple containers with different configurations on the same machine without conflicts.
- Portability: A containerized application includes all its dependencies, configurations, and settings, so it can run the same way across any environment—whether it's your local laptop, an on-premises server, or a cloud environment.
- Lightweight: Unlike VMs, containers don’t require a full OS for each instance. Instead, they share the host OS kernel, which makes them much more efficient in terms of memory and storage.

### What is Docker?

Docker is an open-source platform that automates the deployment, scaling, and management of applications inside containers. It allows developers to package applications and their dependencies into a standardized unit (a container), ensuring that applications can run consistently in any environment, from a developer's local machine to production servers.

Key Docker components:

- Docker Engine: Docker Engine is the core component of Docker that enables containers to run. This is the core service that runs and manages containers.
- Docker Hub: A repository where you can find and share container images. You can pull public images from Docker Hub (e.g., for web servers like Nginx or databases like MySQL) or push your custom images.
- Docker compose: A tool for defining and running multi container docker applications.

### Images and containers

Images are templates for creating containers, like a snapshot of an application at a certain time. Images are immutable, so they dont change once they are created, only way to change them is to recreate the image. The immutability ensures the application runs consistently no matter where its deployed.

Containers are running instances of the image. Containers are what you actually interact with, they run the application.

An image is created using a Dockerfile. A Dockerfile is a text file that contains instructions for building a Docker image. Each instruction in the Dockerfile creates a new layer in the image.

