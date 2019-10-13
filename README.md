# Udemy Ansible Assignment

This is my solution for the Ansible Assignment on Udemy https://www.udemy.com/learn-ansible-advanced

## Infrastructure 

I choose Openstack Private Cloud because I am familiar with it.
To interact with Openstack Private Cloud API, I need to download the Openstack RC file from web interface and source it:

```
source openrc.sh
```

## Development Environment

I am using Arch Linux at my workstation, so I used my workstation to execute the ansible project.

## Ansible Project

I have two playbooks:
* **deploy-instances.yml** : create instances on Openstack Private Cloud
* **site.yml** : install and configure the project of web platform

On the playbooks I used the next roles:

* **flask_web**: deploy web application using flask
* **geerlingguy.haproxy**: external role used to configure load balancer
* **geerlingguy.mysql**: external role used to configure mysql server
* **heat**: create Instances on Openstack Private Cloud using Heat Ochestation Template
* **python**: Install python required packages

The inventory is dynamic and it is the folder inventory with next structure:
* **openstack_inventory.py**: Script to get host information from Openstack Private Cloud. More information at [Working with dynamic inventory : Openstack](https://docs.ansible.com/ansible/latest/user_guide/intro_dynamic_inventory.html#explicit-use-of-openstack-inventory-script). The file openstack.yml is a configuration used by this script.
* **hosts** : have the groups defined at playbook's with the instances
* **group_vars**: configuration of the installed environment.

## General Thanks

I want to thanks Mumshad Mannambeth for this great cource and this good challenge.
