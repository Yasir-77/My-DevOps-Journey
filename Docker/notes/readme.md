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

### Importance in Modern Development

- Simpl;ified Deployment - Applications run consistently across different environments (e.g., development, testing, and production), avoiding the "it works on my machine" issue.
- Imporved effeciency - Traditional virtual machines can be resource heavy and slow to start. Containers share the host OS kernel, making them more lightweight than virtual machines, reducing overhead.
- Enhanced collaboration - Docker makes it easy to share development environments and applications with team members


## IMPORTANT INTERVIEW QUESTION: VMs vs Containers

A virtual machine allows multiple operating systems to run on a single physical machine. At the base you have the infrastructure, this is your physical or virtual hardware. On top of that sits the host operating system which is the primary operating system managing all the resources. Above the host OS is the hypervisor, the hypervisor is responsible for creating and managing virtual machines by allocating resources like CPU, memory and storage. Each virtual machine runs a full guest operating system insolated from the nothers. Within each virtual machine there is a guest operating system which is another operating system running ontop of the host. Each virtual machine would also have its own binaries and libraries and anything else an application needs to run. Within the setup there is strong isolation. Each VM is resource heavy which consumes alot of CPU memory and storage

![image](https://github.com/user-attachments/assets/0e1e91dd-8982-495e-ac5b-7777998f433f)

Containers are a more lightweight and efficient way to isolate applications. They share the host operating systems like VMs, but instead of using a hypervisor, theyll run on the docker engine. The docker engine sits on top of the host operating system and is responsible for running containers. Containers are isolated from each other at a process level, but they share the underlying OS Kernel making them much lighter than VMs. Difference is they dont have guest operating systems because they share the host operating system making them lighter than virtual machines. Within each container you have the application and its dependencies, binaries and libraries. This setup allows containers to start up quickly and use fewer resources compared to VMs

![image](https://github.com/user-attachments/assets/209ad5ec-d370-4c06-81c1-19bf4091bf6b)

###  Key differences between them:

1 - Usage and Startup time:
- VMs are heavier since each VM runs its own operating system. This increases overhead in terms of memory, CPU usage, and disk space. Booting a VM involves starting the entire OS, which can take time.
- Containers are lighter because they share the host's OS kernel. They use less memory and CPU. Containers start almost instantly, as there's no need to boot a full OS.

2 - Isolation:
- VMs provide stronger isolation since each VM runs a separate OS and is abstracted at the hardware level. Better suited for cases where complete isolation between workloads is critical (e.g., multi-tenant environments).
- Containers provide process-level isolation through the use of namespaces and cgroups. This isolation is effective but not as strong as VMs because containers share the OS kernel.

3 - Portability:
- VMs have less portability, can run on different hypervisors and platforms but require hypervisor compatibility. Moving VMs across different environments can be more complex because they carry a full OS and hardware abstraction.
- Containers are highly portable. An application in a container will run the same way regardless of where it's deployed (e.g., on a developer's laptop, in the cloud, or on a production server) as long as there’s a compatible container runtime like Docker.

## Docker images

### Understanding Dockerfile

A Dockerfile is a text file containing instructions on how to build a Docker image. It defines the environment and the steps needed to create a containerized application. Each instruction in the Dockerfile corresponds to a layer in the Docker image, making it easier to manage and track changes.

#### Basic structure:
![image](https://github.com/user-attachments/assets/43d320a0-1095-4d18-b257-08d27e806012)

#### Example Dockerfile:
![image](https://github.com/user-attachments/assets/288d0d9b-0a93-45ef-b2c7-3cb001f1747c)

## Writing a Dockerfile

### First create a docker Git repositry 

Create a docker folder on desktop
```
cd Desktop/Docker
```
Then create a README.md file, Type:
```
echo "# Dockerr Learning" > README.md
```
Then initialise folder as a git repository. Type:
```
git init
```

Then add README.md file to the staging area
```
git add README.md
```

Then commit by typing:
```
git commit -m "Inital commit"
```
Then to change the branch from master to main type:
```
git branch -M main
```

### Creating a simple application to Dockerise

First open the Docker learning file and open the terminal on VSCODE.

Download Python to check this is installed type:
```
python --version
```
Then install Flask, flask is a simple and lightweight framework for creating web applications in Python. type:
```
pip install flask
```
Create a new directory, type:
```
mkdir hello_flask
```
Enter the directory, type:
```
cd hello_flask  
```
Create the appliction type:
```
touch app.py
```
In VSCODE copy the following script in the file:
```
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5002)
```
Code breakdown:
from flask import Flask - This imports the Flask class from the flask module, which allows you to create a Flask web application.

app = Flask(__name__) - This line initializes the Flask application by creating an instance of the Flask class. The __name__ variable is used to indicate the name of the module in which the app is being initialized, which helps Flask locate resources.
python

@app.route('/') - This is a route decorator that defines the URL endpoint (/) for this function. In this case, when a user visits the root of the web app (e.g., http://localhost:5002/), this function will be called.

def hello_world():
    return 'Hello, World!'

This is the function that is executed when a user visits the / route. It simply returns the string 'Hello, World!', which is displayed on the webpage.
python

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5002)

This block ensures that the Flask app runs when the script is executed directly.
The app.run() method starts the Flask development server.
host='0.0.0.0': This allows the server to be accessed externally (not just on localhost but also from other devices on the same network).
port=5002: The application will run on port 5002 (instead of Flask's default port 5000).

To run the code type:
```
python app.py
```

### Containerise web application 1:

- First create a dockerfile type:
```
touch Dockerfile
```
- Write out the contents in the Dockerfile:
```
FROM python:3.8-slim
WORKDIR /app
COPY . .
RUN pip install flask
EXPOSE 5002
CMD [ "python", "app.py" ] 
```
FROM python:3.8-slim - This sets the base image to Python 3.8-slim, which is a smaller, lightweight image of Python, making the resulting container more efficient. The slim version contains only the essentials for running Python applications.

WORKDIR /app - This sets the working directory inside the container to /app. Any commands or files copied will now work relative to this directory.

COPY . . - This copies the contents of the current directory (where your Dockerfile and Python code reside) into the container’s /app directory.

RUN pip install flask - This runs the pip install flask command inside the container, installing Flask into the container’s Python environment.

EXPOSE 5002 - This tells Docker that the container will listen on port 5002, which you set in your Flask app (app.run(host='0.0.0.0', port=5002)).

CMD [ "python", "app.py" ] - This defines the command to run when the container starts. In this case, it starts the Flask app by running python app.py.

- Next step is to build the docker image. Go to command line and type:
```
docker build -t hello-flask .
```
**`docker build`** command initiates the build process

**`-t hello-flask`**  the -t tags the image with a name. In this case the name is hello-flask

The **`.`** represents the current directory and tells docker to look for the docker file there.

Docker will execute each intruction in Docker file. Image will be created and ready to use.


### Containerise web application 2:

With the docker image now built it can be run as a container. To run it as a container type:
```
docker run -d -p 5002:5002 hello-flask
```

Breakdown:

**`docker run`**: Starts a new Docker container from an image.

**`-d`**: Runs the container in detached mode, meaning it runs in the background.

**`-p 5002:5002`**: Maps port 5002 on your local machine (host) to port 5002 inside the container. This allows you to access the Flask app from your browser via http://localhost:5002.

**`hello-flask`**: Specifies the name of the image you built earlier, which Docker will use to create and run the container.

To verify docker container is running type:
```
docker ps
```
The container ID will appear aswell as other information

To stop the container use the command **`docker stop`** followed by the container ID.

## Docker networking

### Basic Networking concepts in Docker

- Bridge network - A bridge network is a default network mode for containers on the same machine. containers connected to the bridge network can communicate with eachother using their own IP addresses. It is isolated from your host machine network which provides an extra layer of security.

- Host network - In host mode, a container uses the host machines network directly without any isolation between the container and the host.

- None network - The none network disables all networking for a container. The container can’t communicate with other containers, the host, or external networks.

Docker networking provides flexibility for container-to-container and container-to-host communication, with a range of networking drivers available to suit different use cases.

### Linking containers together

To link the flask application to a MySQL database container follow the following steps:

#### 1 - Modify the file og the existing flask app to connect to a MySQL database. Copy the following code:
```
# app.py

from flask import Flask
import MySQLdb

app = Flask(__name__)

@app.route('/')
def hello_world():
    # Connect to the MySQL database
    db = MySQLdb.connect(
        host="mydb",    # Hostname of the MySQL container
        user="root",    # Username to connect to MySQL
        passwd="My-secret-pw",  # Password for the MySQL user
        db="mysql"      # Name of the database to connect to
    )
    cur = db.cursor()
    cur.execute("SELECT VERSION()")
    version = cur.fetchone()
    return f'Hello, World! MySQL version: {version[0]}'

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5002)
```
Simple breakdown of code:

1. Imports
```
from flask import Flask
import MySQLdb
```
Flask: This is a lightweight Python web framework used to create web applications.

MySQLdb: This module allows the Flask application to connect to a MySQL database. It provides an interface for running SQL queries and interacting with the MySQL server.

2. Connecting to the MySQL Database
```
db = MySQLdb.connect(
    host="mydb",    # Hostname of the MySQL container
    user="root",    # Username to connect to MySQL
    passwd="my-secret-pw",  # Password for the MySQL user
    db="mysql"      # Name of the database to connect to
)
```
- MySQLdb.connect(): This function establishes a connection to the MySQL database.
- host="mydb": The hostname or IP address where the MySQL server is running. In this case, mydb is used, which would be the hostname of the MySQL container in a Docker Compose setup (since the containers are networked together and can communicate using service names).
- user="root": The MySQL username. Here, the root user is used.
- passwd="My-secret-pw": The password for the root user.
- db="mysql": The name of the database to connect to. In this case, it connects to the default mysql database.

#### 2 - Ensure Dockerfile is set up to install the necessary MySQL client library. Type the code: 
```
FROM python:3.8-slim

WORKDIR /app

COPY . .

RUN apt-get update && apt-get install -y \
    gcc \
    python3-dev \
    libmariadb-dev \
    pkg-config

RUN pip install flask mysqlclient

EXPOSE 5002

CMD ["python", "app.py"]
```
Simple Breakdown of code:

The only changes that are made are:

1. Install System Dependencies
```
RUN apt-get update && apt-get install -y \
    gcc \
    python3-dev \
    libmariadb-dev \
    pkg-config
```
- apt-get update: Updates the package lists in the container to ensure you have the latest version information.
- gcc: The GNU C compiler is required because mysqlclient (a Python package that interacts with MySQL/MariaDB) needs to compile C extensions.
- python3-dev: Provides the header files and libraries needed to build Python packages that require compilation, such as mysqlclient.
- libmariadb-dev: Installs the MariaDB development libraries and headers, which are needed to compile the mysqlclient library (since MySQL and MariaDB are compatible).

pkg-config: Helps in managing compilation of libraries by making it easier to include paths and link necessary libraries.

2.  Install Python Dependencies
```
RUN pip install flask mysqlclient
```
pip install: Installs the required Python packages.

flask: The web framework used to create your application.

mysqlclient: A Python package that allows the Flask app to connect to MySQL/MariaDB databases. Since mysqlclient is a C-based library, it needs to be compiled, which is why the necessary system dependencies were installed earlier.

#### Next step is to build and run the updated containers.

1. Create a custom network - a custom network allows containers to communicate with each other using container names instead of IP addresses. In the integrated terminal in VSCode type:
```
docker network create my-custom-network
```
This will craste a custom network that will be used to connect the flask and MySQL containers together.

2. Run the containers:

To run the MySQL container type:
```
docker run -d --name mydb --network my-custom-network -e MYSQL_ROOT_PASSWORD=(My-secret-pw)
```
**`--name mydb`**: This names the container mydb, which makes it easier to refer to this container in commands or when linking other containers to it.

**`--network my-custom-network`**: Specifies the custom Docker network that the container will join. In this case, it will join the network my-custom-network. This network allows containers to communicate with each other by name (like how app.py connects to mydb).

**`-e MYSQL_ROOT_PASSWORD=your_password`**:

This environment variable sets the root password for the MySQL server inside the container. Replace your_password with a secure password of your choice.

#### Build the docker image for the flask app with the updated docker file. Type the following in the VSCode terminal:
```
docker build -t hello-flask-mysql .
```
Then run the flask application type:
```
docker run -d --name myapp2 --network my-custom-network -p 5002:5002 hello-flask-mysql
```

## Docker compose

### Introduction to Docker compose

Docker compose is a tool that allows you to define and manage multi container docker applications. It simplifies the process of setting up and orchestrating multiple services (containers) that need to work together, such as a web server, a database, or other dependencies, all defined in a single file called docker-compose.yml.With Docker Compose, you can manage containers as a group instead of handling each container individually.

Key features:

- Docker-compose.yml file 
- Commands - 
- Networking

### Importance in DevOps:

- Makes Development and testing easier - instead of manually setting everything, you can define everything in a docker-compose.yml file and run a single command to start the environment.
- Ensures consistency - Ensures that everyone in your team is working in the same environment. By definig the environment in a docker-compose.yml file you guarantee that every developer, tester and CICD pipeline uses the exact same setup.
- Enhances teamwork - Becomes easier to share code configurations and the environment set up itself. Docker-compose makes it easier to version control your infrastructure

### Writing a docker-compose.yml

For the Hello World application that connects to MySQL database, a dock-compose.yml file is going to be created that runs both services with just one command

1- Create Docker-compose.yml file
```
touch docker-compose.yml
```
2- Open the file and type the following code:
```
version: '3.8'

services:
  web:
    build: .
    ports:
      - "5000:5000"
    depends_on:
      - db

  db:
    image: mysql:5.7
    environment:
      MYSQL_ROOT_PASSWORD: my-secret-pw
```
Code Breakdown:

1. Version
```
version: '3.8'
```
This specifies the Compose file format version. Version 3.8 is commonly used with newer Docker features, and it ensures compatibility with Docker's latest capabilities.

2. Services
   
The services: section defines the containers that Docker Compose will create and manage. In this case, there are two services: web and db.
```
  web:
    build: .
    ports:
      - "5002:5002"
    depends_on:
      - db
```
- build: .: This means Docker will build the web service's image from the Dockerfile located in the current directory (.). This is where the application's source code resides, and the Dockerfile defines how to build the app.
- ports:: The web service will expose port 5002 on the host, mapped to port 5002 inside the container. This allows the Flask app to be accessible at http://localhost:5002.
- depends_on:: This specifies that the web service depends on the db service. This means that the db container will be started first before the web service. However, this does not wait for the database to be fully ready (i.e., it doesn’t guarantee the MySQL service is ready to accept connections), so you might still need a retry logic in the web app for connecting to the database.

3. Database (MySQL) Service
```
  db:
    image: mysql:5.7
    environment:
      MYSQL_ROOT_PASSWORD: (My-secret-pw)
```
- image: mysql:5.7: This specifies that the db service will use the MySQL 5.7 image from Docker Hub. This image contains the MySQL server software.
- environment:: This section defines environment variables for the MySQL container.
- MYSQL_ROOT_PASSWORD: This sets the root password for the MySQL server. In this case, it is set to "My-secret-pw". This password will be required to access the MySQL database as the root user.

































