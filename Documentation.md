# Exam Project Documentation

## Project Overview
This project involves the management of two servers, named "Master" and "Slave," both running on Ubuntu. We use Vagrant for automation. A Bash script handles the setup of a LAMP (Linux, Apache, MySQL, PHP) stack and pulls a PHP application from GitHub with all the necessary components. Additionally, the script configures Apache and MySQL.

To make everything run smoothly, we employ Ansible to execute the Bash script on the "Slave" server. There's also a scheduled task (cron job) that checks the server's uptime daily at midnight.

The Bash script is designed to be user-friendly and can be accessed in this repository: [GitHub Repository](https://github.com/TYDev01/Second-Semester-exam.git).

## Provisioning of "Master" and "Slave"
We kick off the project by executing the "vagrant-master.sh" script, which sets up both the Ubuntu "Master" and "Slave" machines and creates a Vagrantfile.

## Laravel Deployment on Master Node
The "lamp-master.sh" script deploys Laravel cloned from the GitHub repository at [GitHub Repository](https://github.com/laravel/laravel) exclusively on the "Master" node.

![Laravel on Master Node](<snapshots/successfully-install-laravel-and-all-dependencies.PNG>)

![Laravel on Master Node](<snapshots/laravel-successfully-installed.PNG>)

![Master IP: 192.168.30.20](<snapshots/laravel-page-with-master-IP-address.PNG>)

## Ansible Playbook
The Ansible Playbook can be found in the "ansible-playbook" directory, which contains the following elements:

#### a. Ansible.cfg:
This file is the central configuration that guides Ansible's behavior, governing all interactions performed by the control node.

#### b. Inventory:
The inventory is a list of managed nodes or hosts that Ansible configures. In this project, the inventory carries the IP address of the "Slave" node.

#### c. play-slave.yml:
The Ansible Playbook outlines automation tasks for the "Slave" node, enabling actions to be executed with minimal manual effort across various IT solutions.

#### d. files:
This directory contains the "lamp-slave.sh" file, which the playbook uses to deploy Laravel cloned from the GitHub repository at [GitHub Repository](https://github.com/laravel/laravel.git).

![Ansible Playbook](<snapshots/installation-of-Ansible-Playbook-to-Slave.PNG>)

![OK=6](<snapshots/continuation-of-Ansible-Playbook-to-Slave.PNG>)

![Slave IP: 192.168.30.21](<snapshots/laravel-page-with-slave-IP-address.PNG>)

Thank you for your time and consideration.