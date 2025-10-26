# Ansible Infrastructure Automation

This repository contains an **Ansible configuration** for provisioning and configuring a simple web and database infrastructure on Amazon Linux 2023 instances.  

It includes:
- An **inventory file** defining the servers and their groups.
- A **playbook** (`site.yml`) to automatically install and configure:
  - Apache (`httpd`) on web servers
  - MariaDB (`mariadb105-server`) on database servers

---

## 🧭 Project Structure

ansible-infra-automation/
├── ansible.cfg # Global Ansible configuration
├── inventory/
│ ├── inventory.yml # Inventory file (hosts, groups, data centers)
│ └── group_vars/
│ ├── webservers.yml # Variables specific to web servers
│ └── dbservers.yml # Variables specific to database servers
│
├── roles/
│ ├── web/ # Role for web server setup
│ │ ├── tasks/
│ │ │ └── main.yml # Web setup tasks (httpd installation, etc.)
│ │ ├── templates/ # Jinja2 templates for httpd config or index.html
│ │ ├── files/ # Static files (optional)
│ │ └── vars/
│ │ └── main.yml # Variables for web role
│ │
│ ├── db/ # Role for database setup
│ │ ├── tasks/
│ │ │ └── main.yml # DB setup tasks (MariaDB installation)
│ │ ├── templates/
│ │ │ └── my.cnf.j2
│ │ ├── files/
│ │ └── vars/
│ │ └── main.yml
│
├── playbooks/
│ ├── site.yml # Main playbook combining all roles
│ ├── web.yml # Playbook for only web servers
│ └── db.yml # Playbook for only database servers
│
├── files/
│ └── clientkey.pem # SSH key (DO NOT COMMIT)
│
├── logs/
│ └── ansible.log # Optional log output file
│
├── LICENSE
└── README.md
