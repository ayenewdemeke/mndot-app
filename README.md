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

Create a `.env` file by copying the example file:

```bash
cp .env.example .env
```

### 2. Install Dependencies

Install the necessary dependencies:

```bash
docker run --rm \
    -v $(pwd):/var/www/html \
    -w /var/www/html \
    laravelsail/php83-composer:latest \
    composer install
```

### 5. Start the Application

Start the Docker containers:

```bash
./vendor/bin/sail up
```

### 3. Configure the Environment File

Generate the application key:

```bash
./vendor/bin/sail artisan key:generate
```

### 4. Build Frontend Assets

```bash
./vendor/bin/sail npm install
./vendor/bin/sail npm run build
```

### 6. Run Database Migrations

Run the following command to set up the required database tables:

```bash
./vendor/bin/sail artisan migrate:fresh --seed
```

Once the containers are up and running, the application will be accessible at [http://localhost](http://localhost).

### 7. Access the Database

The database can be accessed using a tool like MySQL Workbench by using database credentials provided in .env file.

---

The application is now ready and running.
