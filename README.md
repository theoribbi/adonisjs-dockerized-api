# AdonisJS Dockerized API

A simple AdonisJS application using the Lucid ORM with the API preset, fully containerized with Docker and PostgreSQL.

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
  - [1. Clone the Repository](#1-clone-the-repository)
  - [2. Configure Environment Variables](#2-configure-environment-variables)
  - [3. Build and Run with Docker Compose](#3-build-and-run-with-docker-compose)
  - [4. Access the Application](#4-access-the-application)
- [Project Structure](#project-structure)
- [Contributing](#contributing)

## Features

- **AdonisJS**: A Node.js MVC framework.
- **Lucid ORM**: Elegant ORM for interacting with the PostgreSQL database.
- **Dockerized Setup**: Easy deployment and environment consistency using Docker and Docker Compose.
- **PostgreSQL**: Reliable and powerful open-source relational database.

## Prerequisites

- [Docker](https://www.docker.com/get-started) installed on your machine.
- [Docker Compose](https://docs.docker.com/compose/install/) installed.

## Getting Started

Follow these steps to set up and run the project locally.

### 1. Clone the Repository

```bash
git clone https://github.com/theoribbi/adonisjs-dockerized-api.git
cd adonisjs-dockerized-api
```

### 2. Configure Environment Variables
Copy the example environment file and modify it as needed.

```bash
cp .env.example .env
```

Open the .env file in your preferred text editor and update the values if necessary, especially the database configuration to match the Docker setup.

### 3. Build and Run with Docker Compose
Ensure that Docker and Docker Compose are running on your machine. Then, execute the following command to build and start the containers:

```bash
docker-compose up
```
This command will set up the AdonisJS application along with a PostgreSQL database.

### 4. Access the Application 
Once the containers are up and running, you can access the API at:

```bash
http://127.0.0.1:3333
```

## Project Structure
```bash
adonisjs-api/
├── src/
│   ├── app/
│   ├── bin/
│   ├── config/
│   ├── database/
│   ├── start/
│   ├── tests/
│   ├── Dockerfile
│   ├── ace.js
│   ├── adonisrc.ts
│   ├── eslint.config.js
│   ├── package.json
│   └── tsconfig.json
├── .env
├── README.md
└── docker-compose.yml
```

 - ```src/```: Contains the AdonisJS application source code.
    - **app/:** Application code.
    - **bin/:** Binary files.
    - **config/:** Configuration files.
    - **database/:** Database migrations and seeds.
    - **start/:** Entry points and server setup.
    - **tests/:** Test suites.


## Contributing
Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.
