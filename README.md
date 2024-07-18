# WordPress Docker Compose Setup

This project provides a Docker Compose configuration for quickly setting up a WordPress environment with a MariaDB database.

## Overview

The `docker-compose.yml` file in this project defines two services:

1. A MariaDB database service
2. A WordPress service

These services are configured to work together, allowing you to run a WordPress site with a MySQL-compatible database backend.

## Prerequisites

- Docker
- Docker Compose

## Usage

1. Clone this repository or copy the `docker-compose.yml` file to your local machine.

2. Open a terminal and navigate to the directory containing the `docker-compose.yml` file.

3. Run the following command to start the services:

   ```
   docker-compose up -d
   ```

4. Once the containers are up and running, you can access your WordPress site by opening a web browser and navigating to `http://localhost`.

5. To stop the services, run:

   ```
   docker-compose down
   ```

## Configuration

### Database Service

- Uses MariaDB 10.6.4 (focal) image
- Root password: somewordpress
- Database name: wordpress
- Database user: wordpress
- Database password: wordpress
- Exposes ports 3306 and 33060

### WordPress Service

- Uses the latest WordPress image
- Accessible on port 80 of the host machine
- Configured to use the database service

## Data Persistence

The configuration uses Docker volumes to persist data:

- `db_data`: Stores the database files
- `wp_data`: Stores the WordPress files

This ensures that your data is preserved even if the containers are stopped or removed.

## Customization

- To use MySQL instead of MariaDB, uncomment the MySQL image line in the `docker-compose.yml` file.
- You can modify the database credentials and WordPress configuration by editing the environment variables in the `docker-compose.yml` file.

## Note

This setup is suitable for development and testing purposes. For production use, additional security measures and optimizations should be implemented.