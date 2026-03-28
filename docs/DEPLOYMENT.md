# Deployment Guide

## Prerequisites
- Ensure you have Docker and Docker Compose installed on your machine.
- Access to a terminal or command line interface.
- Basic knowledge of Docker concepts.

## Docker Compose Setup Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/ROCyberSolutions/sbom-compliance-tracker.git
   cd sbom-compliance-tracker
   ```
2. Create a `.env` file in the root directory based on the example:
   ```bash
   cp .env.example .env
   ```
3. Modify the `.env` file to set your environment variables, such as:
   - `DB_HOST` - The hostname of your database
   - `DB_USER` - Your database username
   - `DB_PASSWORD` - Your database password
   - `DB_NAME` - The name of your database

4. Start the application using Docker Compose:
   ```bash
   docker-compose up -d
   ```

## Environment Variables Configuration
- Review the `.env` file for essential environment variables and their descriptions.
- Customize them according to your deployment needs.

## Manual Deployment Instructions
1. Build the Docker images:
   ```bash
   docker-compose build
   ```
2. Start the services:
   ```bash
   docker-compose up
   ```
3. To stop the services:
   ```bash
   docker-compose down
   ```

## Production SSL/TLS Setup
1. Obtain an SSL certificate.
2. Configure your web server (e.g., Nginx or Apache) to handle HTTPS traffic.
3. Update the Docker Compose file to include the SSL configuration.

## Database Backup Procedures
- Run the following command to backup the database:
  ```bash
  docker exec -t <database_container_name> pg_dumpall -c -U <username> > /path/to/backup.sql
  ```
- Replace `<database_container_name>` and `<username>` accordingly.

## Health Checks
- Ensure your application is running by checking the following endpoints:
  - `/health`
  - `/status`

Use tools like `curl` to monitor the health:
```bash
curl -I http://localhost/health
```

## Troubleshooting Section
- If the application fails to start:
  - Check the logs: `docker-compose logs`
  - Ensure all environment variables are set correctly.
- Common issues:
  - Ports already in use.
  - Incorrect database credentials.

## Monitoring Guidelines
- Use monitoring tools like Prometheus and Grafana to visualize and monitor your application's performance.
- Set up alerts for critical failures and health checks.