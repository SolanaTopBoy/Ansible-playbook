# Ansible Infrastructure Automation

This repository contains an **Ansible configuration** for provisioning and configuring a simple web and database infrastructure on Amazon Linux 2023 instances.  

It includes:
- An **inventory file** defining the servers and their groups.
- A **playbook** (`playbook.yml`) to automatically install and configure:
  - Apache (`httpd`) on web servers
  - MariaDB (`mariadb105-server`) on database servers
