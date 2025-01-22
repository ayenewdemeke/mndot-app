# MnDOT App Setup Guide

This guide explains how to configure and run the MnDOT App.

---

## Prerequisite

- Docker must be installed and running.
- The application should be run on macOS, Linux, or Windows Subsystem for Linux (WSL2).

---

## Steps to Set Up and Run the App

### 1. Clone the Repository

Run the following command to clone the repository and navigate to the project directory:

```bash
git clone https://github.com/ayenewdemeke/mndot-app.git mndot-app
cd mndot-app
```

### 2. Configure the Environment File

Create a `.env` file by copying the example file:

```bash
cp .env.example .env
```

Generate the application key:

```bash
./vendor/bin/sail artisan key:generate
```

### 3. Install Dependencies

Install the necessary dependencies:

```bash
composer install
```

### 4. Build Frontend Assets

```bash
npm install
npm run build
```

### 5. Start the Application

Start the Docker containers:

```bash
./vendor/bin/sail up
```

### 6. Run Database Migrations

Run the following command to set up the required database tables:

```bash
./vendor/bin/sail artisan migrate
```

Once the containers are up and running, the application will be accessible at [http://localhost](http://localhost).

### 7. Access the Database

The database can be accessed using a tool like MySQL Workbench by using database credentials provided in .env file.

---

The application is now ready and running.
