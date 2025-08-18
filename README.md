# 2.6-Website Setup Guide

This guide will walk you through setting up the 2.6-Website project locally.

## Prerequisites

Before starting, ensure you have the following installed:
- [Poetry](https://python-poetry.org/docs/#installing-with-pipx) for Python dependency management
- [Bun](https://bun.sh) for JavaScript package management

## 1. Clone the Repository

First, clone the repository including all submodules:

```bash
git clone --recursive https://github.com/Bentheminernz/2.6-Website
```

## 2. Backend Setup

### 2.1 Install Python Environment

Navigate to the backend directory and set up the Python virtual environment:

```bash
cd ./backend
poetry install
poetry self add poetry-plugin-shell
poetry shell
```

### 2.2 Run Database Migration

Set up the database by running migrations:

```bash
python manage.py migrate
```

### 2.3 Create Superuser Account

Create an admin user account:

```bash
python manage.py createsuperuser
```

### 2.4 Initialize Default Games

Set up the default games in the database:

```bash
python manage.py create_games
```

### 2.5 Start the Django Server

Run the backend server:

```bash
python manage.py runserver 127.0.0.1:8070
```

## 3. Frontend Setup

### 3.1 Install Dependencies

In a new terminal window, navigate to the frontend directory and install dependencies:

```bash
cd ./frontend
bun install
```

### 3.2 Start the Development Server

Run the frontend development server (keep this running alongside the backend):

```bash
bun vite
```

## Running the Application

Once both servers are running:
- Backend: `http://127.0.0.1:8070` (You can access the admin portal at `http://127.0.0.1:8070/admin`)
- Frontend: Check your terminal for the Vite development server URL (for this project it should be `http://localhost:5174`)

Make sure both servers are running simultaneously for the application to work properly.