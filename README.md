
# Odoo Installation and Setup in PyCharm

This repository provides step-by-step instructions on how to install and set up Odoo in PyCharm on Windows, macOS, and Linux.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Windows Installation](#windows-installation)
- [macOS Installation](#macos-installation)
- [Linux Installation](#linux-installation)
- [PyCharm Setup](#pycharm-setup)
- [Running Odoo](#running-odoo)

## Prerequisites

Before you begin, ensure you have the following installed on your system:

- Python 3.7+
- Git
- Node.js
- NPM (Node Package Manager)
- PostgreSQL
- PyCharm IDE

## Windows Installation

### Step 1: Install Dependencies

1. **Install Python:**
   - Download and install Python from the [official website](https://www.python.org/downloads/).

2. **Install PostgreSQL:**
   - Download and install PostgreSQL from the [official website](https://www.postgresql.org/download/windows/).

3. **Install Node.js and NPM:**
   - Download and install Node.js (which includes NPM) from the [official website](https://nodejs.org/en/).

### Step 2: Clone the Odoo Repository

Open a command prompt and run the following commands:

```sh
git clone https://github.com/odoo/odoo.git
cd odoo
git checkout 14.0  # Replace with your desired Odoo version
```

### Step 3: Install Python Dependencies

```sh
pip install -r requirements.txt
```

### Step 4: Configure PostgreSQL

Create a new PostgreSQL database user and a database for Odoo.

```sh
psql -U postgres
CREATE USER odoo WITH PASSWORD 'odoo';
CREATE DATABASE odoo OWNER odoo;
```

## macOS Installation

### Step 1: Install Dependencies

1. **Install Python:**
   - Install Python using Homebrew:
     ```sh
     brew install python
     ```

2. **Install PostgreSQL:**
   - Install PostgreSQL using Homebrew:
     ```sh
     brew install postgresql
     ```

3. **Install Node.js and NPM:**
   - Install Node.js (which includes NPM) using Homebrew:
     ```sh
     brew install node
     ```

### Step 2: Clone the Odoo Repository

Open a terminal and run the following commands:

```sh
git clone https://github.com/odoo/odoo.git
cd odoo
git checkout 14.0  # Replace with your desired Odoo version
```

### Step 3: Install Python Dependencies

```sh
pip install -r requirements.txt
```

### Step 4: Configure PostgreSQL

Create a new PostgreSQL database user and a database for Odoo.

```sh
psql -U postgres
CREATE USER odoo WITH PASSWORD 'odoo';
CREATE DATABASE odoo OWNER odoo;
```

## Linux Installation

### Step 1: Install Dependencies

1. **Install Python:**
   - Install Python using your package manager. For example, on Ubuntu:
     ```sh
     sudo apt update
     sudo apt install python3 python3-pip
     ```

2. **Install PostgreSQL:**
   - Install PostgreSQL using your package manager. For example, on Ubuntu:
     ```sh
     sudo apt install postgresql postgresql-contrib
     ```

3. **Install Node.js and NPM:**
   - Install Node.js (which includes NPM) using your package manager. For example, on Ubuntu:
     ```sh
     sudo apt install nodejs npm
     ```

### Step 2: Clone the Odoo Repository

Open a terminal and run the following commands:

```sh
git clone https://github.com/odoo/odoo.git
cd odoo
git checkout 14.0  # Replace with your desired Odoo version
```

### Step 3: Install Python Dependencies

```sh
pip3 install -r requirements.txt
```

### Step 4: Configure PostgreSQL

Create a new PostgreSQL database user and a database for Odoo.

```sh
sudo -u postgres createuser --createdb --username postgres --no-createrole --no-superuser --pwprompt odoo
sudo -u postgres createdb --username postgres --owner odoo odoo
```

## PyCharm Setup

### Step 1: Open PyCharm and Create a New Project

1. Open PyCharm.
2. Click on `File` -> `Open` and select the Odoo directory.

### Step 2: Configure the Python Interpreter

1. Go to `File` -> `Settings` (or `PyCharm` -> `Preferences` on macOS).
2. Select `Project: <your_project_name>` -> `Python Interpreter`.
3. Click on the gear icon and select `Add...`.
4. Choose `Existing environment` and select the Python interpreter from your environment.

### Step 3: Configure Run/Debug Configuration

1. Go to `Run` -> `Edit Configurations`.
2. Click on the `+` icon and select `Python`.
3. Name your configuration (e.g., `Odoo Server`).
4. Set the `Script path` to the `odoo-bin` file in the Odoo directory.
5. Set the `Parameters` to `-c odoo.conf` (or any configuration file you set up).
6. Set the `Working directory` to the Odoo directory.
7. Apply the changes.

## Running Odoo

### Step 1: Create a Configuration File

Create a configuration file `odoo.conf` in the Odoo directory with the following content:

```ini
[options]
addons_path = addons
db_host = False
db_port = False
db_user = odoo
db_password = odoo
db_name = odoo
```

### Step 2: Run Odoo

Run the Odoo server using the configuration set up in PyCharm.

1. Select the run configuration you created (e.g., `Odoo Server`).
2. Click on the `Run` button (green triangle) to start the Odoo server.

### Step 3: Access Odoo

Open your web browser and go to `http://localhost:8069`. You should see the Odoo login page.
