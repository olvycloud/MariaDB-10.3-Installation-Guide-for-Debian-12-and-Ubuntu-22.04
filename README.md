# MariaDB 10.3 Installation Guide for Debian 12 and Ubuntu 22.04

This guide provides step-by-step instructions to install MariaDB 10.3 on Debian 12 and Ubuntu 22.04 systems using the Olvy repository.

> **Note:** MariaDB 10.3 reached its end of life in May 2023 and is no longer supported by the vendor.  
> This installation serves as a transitional solution to address performance issues during migration.  
> It is recommended to update your queries and transition to the latest MariaDB versions for enhanced security and stability.  
> [Read more on Olvy.net](https://olvy.net/blog/olvy-ported-mariadb103-to-debian12-and-ubuntu2204/)

## Prerequisites

- **Operating Systems Supported:**
  - Debian 12 "bookworm"
  - Ubuntu 22.04 LTS "Jammy Jellyfish"

- **Architectures Supported:**
  - x86-64
  - Arm64

## Installation Steps

### 1. Add Olvy Repository

Edit the `sources.list` file to include the Olvy repository:

```bash
sudo nano /etc/apt/sources.list
```

Add the appropriate repository line based on your operating system:

 - Debian 12 "Bookworm", x86-64:
```
deb [trusted=yes] https://repo.olvycloud.com/mariadb/10.3/bookworm /
```
 
 - Debian 12 "Bookworm", Arm64:
```
deb [trusted=yes] https://repo.olvycloud.com/mariadb/10.3/bookworm-arm64 /
```
 
 - Ubuntu 22.04 LTS "Jammy Jellyfish", x86-64:
```
deb [trusted=yes] https://repo.olvycloud.com/mariadb/10.3/jammy /
```
 
 - Ubuntu 22.04 LTS "Jammy Jellyfish", Arm64:
```
deb [trusted=yes] https://repo.olvycloud.com/mariadb/10.3/jammy-arm64 /
```

Save and exit the editor.

### 2. Update Package Indexes
Refresh the package lists to include the new repository:

```bash
sudo apt update
```

### 3. Install Dependencies
Install the necessary dependencies:

```bash
sudo apt install mysql-common mariadb-common galera-3
```

### 4. Install MariaDB 10.3
Proceed to install the MariaDB server and client:

```bash
sudo apt install mariadb-server-10.3 mariadb-client-10.3
```

## Post-Installation
After installation, verify the MariaDB service status:

```bash
sudo systemctl status mariadb
```

Secure your MariaDB installation by running:

```bash
sudo mysql_secure_installation
```

## Important Considerations

- *Performance Issues:* Some database queries may experience performance degradation due to changes introduced in MariaDB versions post-10.3, such as the Rowid Filtering Optimization implemented in MariaDB 10.4.3. This installation aims to mitigate such issues during migration.

- *Security Notice:* Since MariaDB 10.3 is no longer supported, it is advisable to plan an upgrade to a supported version to ensure ongoing security updates and support.

## About Olvy

Olvy is a private and independent Limited Liability Company based in Bratislava, Slovakia, offering innovative and reliable Managed Cloud Hosting services. 
OLVY CLOUD

For more information, visit [Olvy's website](https://olvy.net/).


