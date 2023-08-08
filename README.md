# Brainstorm-Tech

# My WordPress Website

## Description

This repository contains the code for my WordPress website. It includes the necessary files to set up the website locally for development and deploy it to a remote server using GitHub Actions.

## Local Development Setup

To set up the website locally for development, follow these steps:

1. Install the required software:
   - Git: Install Git on your local machine from https://git-scm.com/downloads.
   - PHP: Install PHP 7.4 or later on your machine. You can use XAMPP or WAMP for easy setup.
   - MySQL: Install MySQL to create a local database for WordPress. You can use XAMPP or WAMP, which includes MySQL.
   - Nginx (or any other web server): Install and configure Nginx to serve your WordPress files. Alternatively, you can use Apache or other web servers.

2. Download WordPress:
   - Go to https://wordpress.org/download/ and download the latest version of WordPress.
   - Extract the downloaded WordPress archive to a folder on your local machine.

3. Configure Nginx (or your web server of choice):
   - Set up a new virtual host in Nginx to point to the WordPress folder you extracted in the previous step.
   - Make sure the web server is configured to process PHP files.

4. Create a MySQL Database:
   - Create a new MySQL database for your WordPress website.
   - Create a MySQL user and grant necessary privileges to the database.

5. Configure WordPress:
   - Rename the `wp-config-sample.php` file in the WordPress folder to `wp-config.php`.
   - Open `wp-config.php` in a text editor and update the database connection settings with the database name, username, and password you created in the previous step.

6. Set Up WordPress:
   - Access your website in a web browser (localhost or the domain you set up with Nginx).
   - Follow the on-screen instructions to set up your WordPress admin account, website title, and other basic settings.

## GitHub Actions Deployment

This repository is configured with GitHub Actions to automatically deploy the website to a remote server (VPS) whenever changes are pushed to the main branch.

### Prerequisites

To use GitHub Actions for deployment, you need the following:

- A Virtual Private Server (VPS) with a secure Linux distribution (e.g., Ubuntu 22.04) and Nginx, MySQL, and PHP installed.
- A domain name or IP address for the VPS.
- A GitHub account with administrative access to this repository.

### Deploy the Website

1. Set Up SSH Key:
   - Generate a new SSH key on your local machine (if you don't have one already) using the command `ssh-keygen`.
   - Add your public SSH key to your VPS's `~/.ssh/authorized_keys` file.
   - In your GitHub repository, go to "Settings" > "Secrets" and add the following secrets:
     - `SSH_PRIVATE_KEY`: Your private SSH key (including the -----BEGIN RSA PRIVATE KEY----- and -----END RSA PRIVATE KEY----- parts) in PEM format.
     - `EC2_INSTANCE_IP`: The IP address or domain of your VPS.

2. Push Changes:
   - Make changes to your WordPress website code locally.
   - Commit and push the changes to the main branch of this repository.

3. GitHub Actions will automatically deploy the changes to your VPS.

4. Access your website using the VPS IP address or domain to see the changes live.

