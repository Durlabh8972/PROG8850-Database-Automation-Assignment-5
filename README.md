README.md in your project folder:

markdown
Copy
Edit
# PROG8850 Assignment 5 - MySQL Index Timing Script

## Overview

This project contains a Python script to connect to a MySQL database and run timing tests on various SQL queries, including scalar queries and full-text search queries. The script runs EXPLAIN statements (where applicable) and measures execution times, outputting the results to the console and a summary file.

---

## Prerequisites

- Python 3.x
- MySQL Server running and accessible (default port 3306 or 3307 as per your setup)
- Python package `mysql-connector-python`

---

## Setup Instructions

1. **Clone or download this repository to your workspace.**

2. **Install the required Python package:**

   ```bash
   pip install mysql-connector-python
Prepare your MySQL database:

Ensure your MySQL server is running.

Create and populate the orders table in your database.

Make sure full-text indexes exist on the columns used in full-text search queries (e.g., description).

Configure environment variables (optional):

By default, the script connects using:

Host: 127.0.0.1

Port: 3307

User: root

Password: Secret5555

Database: prog8850

You can override these by setting environment variables before running the script:

bash
Copy
Edit
export DB_HOST=your_host
export DB_PORT=your_port
export DB_USER=your_user
export DB_PASSWORD=your_password
export DB_NAME=your_database
Run the timing script:

bash
Copy
Edit
python3 path/to/index_timing.py
Replace path/to/index_timing.py with the actual path, for example:

bash
Copy
Edit
python3 ./.devcontainer/scripts/index_timing.py
Script Details
The script runs three queries:

Count of orders where amount > 500

Average amount for orders between 10 and 200

Full-text search for "running shoes" in the description column

For scalar queries (COUNT, AVG), EXPLAIN is skipped due to MySQL limitations.

Execution times are printed and median timings are saved in timings_summary.txt.

Troubleshooting
Connection errors:

Ensure MySQL is running and accessible on the specified host and port.

Full-text index errors:

Make sure the full-text index exists on the description column:

sql
Copy
Edit
ALTER TABLE orders ADD FULLTEXT(description);
Load data errors:

If loading CSV data into MySQL, ensure the file path is correct and local_infile is enabled:

sql
Copy
Edit
SET GLOBAL local_infile = 1;
Contact
For any issues or questions, please contact:

Your Name: Durlabh Tilavat, Dhyey Patel, Dwarkesh Nasit
Group No: Group 5

Email: Dtilavat8972@conestogac.on.ca

