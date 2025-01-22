# MnDOT App Setup Guide

This guide explains how to configure and run the MnDOT App using Laravel Sail. Follow these steps to ensure everything is set up properly for easy deployment and usage.

---

## Prerequisite

- Docker must be installed and running.

---

## Steps to Set Up and Run the App

### 1. Clone the Repository

Run the following command to clone the repository and navigate to the project directory:

```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
```

### 2. Configure the Environment File

Create a `.env` file by copying the example file:

```bash
cp .env.example .env
```

Ensure the `.env` file has the correct settings for the application. For example:

```dotenv
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=sail
DB_PASSWORD=password
```

### 3. Install Dependencies

Install the necessary dependencies:

```bash
composer install
```

### 4. Start the Application

Start the Docker containers:

```bash
./vendor/bin/sail up
```

Once the containers are up and running, the application will be accessible at [http://localhost](http://localhost).

### 5. Run Database Migrations

Run the following command to set up the required database tables:

```bash
./vendor/bin/sail artisan migrate
```

---

The application is now ready and running.