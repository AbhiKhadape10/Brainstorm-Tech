# Additional Instructions and Explanations

## Deployment Architecture

The WordPress website is deployed using a LEMP stack (Linux, Nginx, MySQL, PHP) on a Virtual Private Server (VPS). The deployment process is automated using GitHub Actions, which ensures a seamless and consistent deployment workflow.

**Components:**
- **Nginx**: Acts as the web server and handles incoming HTTP requests.
- **MySQL**: The database server used to store WordPress data.
- **PHP-FPM**: Handles PHP processing for dynamic content.
- **GitHub Actions**: Automates the deployment process from code changes to updating the website on the VPS.

## Environment Variables
In the GitHub Actions workflow, we use the following environment variables defined in the repository Secrets:

- HOST: The IP address or domain of the VPS where the website will be deployed.
- USERNAME: The username used to log in to the VPS via SSH.
- PRIVATE_KEY: The private SSH key for authentication during deployment.
- PORT: The SSH port used for connecting to the VPS (default: 22).

## Security Measures
To enhance security, the following measures have been implemented:

- Restricted SSH access by using a custom SSH key and disabling password authentication.
- Configured firewall rules to only allow incoming traffic on ports 22 (SSH), 80 (HTTP), and 443 (HTTPS).
- Secured the WordPress installation with strong passwords and limited user privileges.
- Implemented SSL/TLS using Let's Encrypt for encrypted communication between clients and the server.

## Performance Optimization
To improve website performance, the following optimizations have been applied:

- Nginx server configured with caching to reduce server response time.
- Gzip compression enabled to reduce the size of transmitted data.
- Leveraging PHP-FPM to efficiently process PHP scripts and reduce resource usage.

## Troubleshooting Guide

Issue: Website shows "502 Bad Gateway" error.
Solution: This error usually occurs when there is an issue with the Nginx server or PHP-FPM. Check the Nginx error logs and PHP-FPM logs for more details on the error. Ensure that PHP-FPM is running and properly configured in the Nginx server block.

Issue: Website displays a blank page.
Solution: A blank page might be caused by a PHP error. Check the PHP error logs for any reported issues. Additionally, ensure that the file permissions for the WordPress files and directories are set correctly.

