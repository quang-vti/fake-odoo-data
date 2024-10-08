# Fake Odoo data

## Description
This project utilizes the Python `faker` library to generate realistic-looking but fake data for customers, products, and orders. This data can be useful for testing, development, or demonstration purposes. 

## Getting Started

### Prerequisites

* Python 3.x installed ([https://www.python.org/downloads/](https://www.python.org/downloads/))
* Python `faker` library, you can using faker_commerce, faker_food inside this library

   ```bash
   pip install faker
    ```

### Installation

1. **Copy the sample file:**
   ```bash
   cp common_sample.py common.py
    ```
2. **Database Configuration:**
   * Open `common.py` in a text editor.
   * Locate the database connection settings.
   * Update the following with your database credentials:
     * Hostname/IP Address
     * Database Name
     * Username
     * Password

### Usage

1. **Update `run.sh`:**
   * Open the `run.sh` file in a text editor.
   * Adjust the following parameters to control the amount of data generated:
     ```bash
     TOTAL_CUSTOMERS=2000 
     TOTAL_PRODUCTS=100000 
     TOTAL_SO=10000000  
     BATCH_SIZE=1000 
     ```

2. **Run the script:**
   ```bash
   python3 -m run.sh

   ```
3. **Run multiple  SO script process with parallel:**
if you want to run multiple process to quick create SO
   * Install parallel
   ```bash
   sudo apt install parallel
   ```

   * Start your script
   ```bash
   nohup parallel python run_so.py ::: {1..8} > output.log 2>&1 &
   ```
