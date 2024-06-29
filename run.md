
# Running Odoo in a Virtual Environment

This guide provides step-by-step instructions for running Odoo within a Python virtual environment.

## Prerequisites

Make sure you have the following installed on your system:

- Python 3.7+
- Virtualenv

## Steps

### Step 1: Clone the Odoo 17 Repository

Open a terminal (Command Prompt on Windows, Terminal on macOS and Linux) and run the following command to clone the Odoo 17 repository:

```sh
git clone -b 17.0 https://www.github.com/odoo/odoo.git --depth 1
```

### Step 2: Create a Virtual Environment

1. **Navigate to the Odoo Directory:**

   ```sh
   cd odoo
   ```

2. **Create the Virtual Environment:**

   Run the following command to create a virtual environment named `venv`:

   ```sh
   python -m venv venv
   ```

3. **Activate the Virtual Environment:**

   - On Windows:
     ```sh
     venv\Scripts\activate
     ```
   - On macOS and Linux:
     ```sh
     source venv/bin/activate
     ```

### Step 3: Install Dependencies

1. **Upgrade pip:**

   Ensure pip is up-to-date:

   ```sh
   pip install --upgrade pip
   ```

2. **Install Odoo Dependencies:**

   Install all necessary dependencies using the `requirements.txt` file:

   ```sh
   pip install -r requirements.txt
   ```

### Step 4: Configure PostgreSQL

Create a new PostgreSQL database user and a database for Odoo (if not already done):

```sh
psql -U postgres
CREATE USER odoo WITH PASSWORD 'odoo';
CREATE DATABASE odoo OWNER odoo;
```

### Step 5: Create a Configuration File

Create a configuration file named `odoo.conf` in the Odoo directory with the following content:

```ini
[options]
addons_path = addons
db_host = False
db_port = False
db_user = odoo
db_password = odoo
db_name = odoo
```

### Step 6: Run the Odoo Server

Start the Odoo server within the virtual environment using the following command:

```sh
./odoo-bin -c /path/to/your/odoo.conf
```

- On Windows:
  ```sh
  python odoo-bin -c C:\path\to\your\odoo.conf
  ```

### Step 7: Access Odoo

Open your web browser and navigate to `http://localhost:8069`. You should see the Odoo login page.

## Deactivating the Virtual Environment

When you are finished working with Odoo, you can deactivate the virtual environment by running:

```sh
deactivate
```

---

Follow these steps each time you need to run Odoo in your virtual environment. If you have any questions or encounter any issues, feel free to reach out for assistance.
