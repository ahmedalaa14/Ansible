# Ansible Deployment Scripts

This repository contains Ansible playbooks and roles for deploying various applications and services, including Docker, Node.js, Nexus, and Kubernetes on different servers.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Usage](#usage)
- [Playbooks](#playbooks)
- [Roles](#roles)
- [Variables](#variables)
- [License](#license)

## Prerequisites

- Ansible 2.9 or higher
- Python 3.6 or higher
- SSH access to the target servers
- AWS credentials for EC2 inventory plugin

## Usage

1. Clone the repository:
    ```sh
    git clone https://github.com/ahmedalaa14/Ansible.git
    cd Ansible
    ```

2. Update the `hosts` file with your server details.

3. Update the `project-vars` file with your project-specific variables.

4. Run the desired playbook:
    ```sh
    ansible-playbook -i hosts deploy-docker-ec2-user.yaml
    ```

## Playbooks

- **deploy-docker-ec2-user.yaml**: Installs Docker and Docker Compose on EC2 instances and starts Docker containers.
- **deploy-docker-with-roles.yaml**: Similar to `deploy-docker-ec2-user.yaml` but uses roles for better organization.
- **deploy-nexus.yaml**: Installs and configures Nexus Repository Manager.
- **deploy-node.yaml**: Installs Node.js and npm, creates a new user, and deploys a Node.js application.
- **deploy-to-eks.yaml**: Deploys an application to an EKS cluster.
- **my-playbook.yaml**: Configures an Nginx web server.

## Roles

- **create_user**: Creates a new Linux user and adds them to specified groups.
- **start_containers**: Copies Docker Compose files, logs into Docker, and starts containers.

## Variables

- **project-vars**: Contains project-specific variables such as version, location, and Docker credentials.
