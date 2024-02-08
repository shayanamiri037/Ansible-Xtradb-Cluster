# Percona XtraDB Cluster Deployment

This repository contains Ansible scripts for deploying Percona XtraDB Cluster, a high-performance MySQL clustering solution.

## Overview

This project uses Ansible playbooks to easily set up Percona XtraDB Cluster on multiple nodes, installs ProxySQL, and connects the proxy to the database nodes .

## Prerequisites

Before using this playbook, ensure that the following prerequisites are met:

- Ansible is installed on the machine running the playbook.
- Servers/nodes are available with root or sudo access.

## Getting Started

### Ansible Playbook

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/shayanamiri037/Ansible-Xtradb-Cluster
   cd Ansible-Xtradb-Cluster
   
2. Define your server nodes in the inventory.ini file:

   ```bash
   [all]
   node1 ansible_host=your-node1-ip ansible_user=your-ssh-user
   node2 ansible_host=your-node2-ip ansible_user=your-ssh-user
   node3 ansible_host=your-node3-ip ansible_user=your-ssh-user
   .
   .
   .
   
   [database_nodes]
   node1 ansible_host=your-node1-ip ansible_user=your-ssh-user
   node2 ansible_host=your-node2-ip ansible_user=your-ssh-user
   node3 ansible_host=your-node3-ip ansible_user=your-ssh-user
   .
   .
   .

3. Set your root password and your proxysql password in password.yaml file.
4. Customize the MySQL configuration in my.cnf.j2 to suit your requirements.
5. Customize the Proxysql configuration in proxysql_admin_config.j2 and proxysql_config.j2 to suit your requirements.
6. Run the playbook.yaml

   ```bash
   ansible-playbook -i inventory.ini play.yaml
