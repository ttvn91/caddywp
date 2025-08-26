# **CaddyWP**


**CaddyWP** is an open-source tool designed to simplify the deployment and management of multiple WordPress sites behind a lightweight reverse proxy. It uses Docker and Bash scripts to automate configuration, allowing you to quickly set up and scale your WordPress instances with minimal effort.


## **Table of Contents**

- [**CaddyWP**](#caddywp)
  - [**Table of Contents**](#table-of-contents)
  - [**Features**](#features)
  - [**Getting Started**](#getting-started)
    - [**Prerequisites**](#prerequisites)
    - [**Installation**](#installation)
  - [**Usage**](#usage)
  - [**How It Works**](#how-it-works)
    - [**Caddy (Reverse Proxy)**](#caddy-reverse-proxy)
    - [**WordPress (Site Containers)**](#wordpress-site-containers)
    - [**Dedicated Database (MariaDB)**](#dedicated-database-mariadb)
    - [**Bash Script Automation**](#bash-script-automation)
  - [**Default Plugins and Theme**](#default-plugins-and-theme)
    - [Pre-installed Plugins](#pre-installed-plugins)
    - [Default Theme](#default-theme)
  - [**phpMyAdmin**](#phpmyadmin)
  - [**License**](#license)
  - [**Acknowledgements**](#acknowledgements)

---

## **Features**

- **Multiple WordPress Sites**: Easily manage multiple WordPress sites, each running in its own container.
- **Reverse Proxy Integration**: Leverages Caddy for efficient traffic routing and automatic SSL certificate management.
- **Containerized Environment**: Fully Dockerized for simplicity, portability, and scalability.
- **Bash Automation**: Intuitive Bash scripts automate site configuration and deployment.
- **Effortless Scaling**: Add or remove WordPress sites with ease, scaling as your needs grow.

---

## **Getting Started**

### **Prerequisites**

Ensure you have the following installed:

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
- A Unix-based environment (Linux or macOS) or WSL on Windows

### **Installation**

1. **Clone the repository**:
    ```bash
    git clone https://github.com/ttvn91/caddywp.git
    cd caddywp
    ```

2. **Run the install script**:
    ```bash
    ./caddywp.sh
    ```

---

## **Usage**

   ```
   ./caddywp.sh                               - Interactive Menu
   ./caddywp.sh list                          - List all installed WordPress sites
   ./caddywp.sh install <domain>              - Install a new WordPress site
   ./caddywp.sh stop <domain>                 - Stop a running WordPress sites
   ./caddywp.sh start <domain>                - Start an installed WordPress sites
   ./caddywp.sh restart <domain>              - Restart an installed WordPress sites
   ./caddywp.sh delete <domain>               - Delete a WordPress site
   ./caddywp.sh delete all                    - Delete everything
   
   ```

## **How It Works**

caddywp simplifies the deployment and management of multiple WordPress websites by using Docker containers and Caddy as a reverse proxy. Hereâ€™s a breakdown of the key components and how they work together:

### **Caddy (Reverse Proxy)**
Caddy acts as the reverse proxy, automatically handling SSL certificate generation and secure HTTPS connections for all WordPress sites. It efficiently routes incoming traffic to the correct site based on the domain name, ensuring seamless and secure access.

### **WordPress (Site Containers)**
Each WordPress site runs in its own dedicated Docker container. This isolation ensures that each site has its own environment, minimizing the risk of conflicts between sites and making it easy to manage and update individual sites.

### **Dedicated Database (MariaDB)**
Unlike traditional setups where multiple sites share a single database, caddywp creates a **dedicated MariaDB database** for each WordPress site. This offers several advantages:

- **Improved Isolation**: Each site operates independently with its own database, reducing the risk of cross-site issues.
- **Easier Migration**: Since each site has a self-contained database, migrating sites to a new host is straightforward and doesnâ€™t require any reconfiguration of the shared database.
- **Better Performance**: By isolating the databases, you can better manage the performance and resources for each individual site.

### **Bash Script Automation**
caddywp leverages Bash scripts to automate key tasks such as site creation, listing existing sites, and deleting sites. The automation ensures that you can manage your WordPress instances with minimal manual effort and reduced chances of human error.

By combining these components, caddywp offers a fast, efficient, and scalable solution for managing multiple WordPress websites with minimal configuration.

---
## **Default Plugins and Theme**
Each WordPress installation comes pre-configured with carefully selected plugins and theme to enhance your site's functionality right from the start:

### Pre-installed Plugins
- **All-in-One WP Migration and Backup**: Export or import your database, media, plugins, and themes with just a few clicks
- **Redis Object Cache**: A persistent object cache backend powered by Redis
- **Cache Enabler**: Efficient caching plugin for improved performance

These default installations ensure that your WordPress sites are ready for production use with essential SEO, performance, and email functionality out of the box.

---

## **phpMyAdmin**

To use phpMyAdmin with your WordPress sites, follow these steps:

1. **Choose to Include phpMyAdmin During Site Creation**:
   When you are running the installation script to create a new WordPress site, you'll be prompted to include phpMyAdmin. Make sure to opt for PhpMyAdmin during this setup.

2. **Access phpMyAdmin**:
    To access phpMyAdmin, navigate to <http://your-domain.com/pma> (replace "your-domain.com" with your actual domain name).

3.  **Stop phpMyAdmin**:
    To prevent unauthorized access to phpMyAdmin after use, make sure to stop the container. Navigate to your WordPress project directory and execute the following command:
    ```bash
    docker compose stop phpmyadmin
    ```

---

## **License**

This project is licensed under the MIT License - see the LICENSE file for details.

---

## **Acknowledgements**

- [Caddy](https://caddyserver.com/)
- [WordPress](https://wordpress.org/)
- [Docker](https://www.docker.com/)
- [MariaDB](https://mariadb.org/)
- [phpMyAdmin](https://www.phpmyadmin.net/)

---

<p align="right">(<a href="#top">back to top</a>)</p>
