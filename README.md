# Vagrant Ansible Example

## Description

This is a simple showcase example of using Configuration Management tools to provision a Virtual Machine.
*Vagrant* and *Ansible* have been used to provide the Virtual Machine environment and to configure it.

This example will spin up a new Vagrant box (Ubuntu 14.05), and provision it:
    1. Install Nginx as the main web server
    2. Collect all guest machine users
    3. Create an appropriate html file containing all the userrs
    4. Serve the static html file via Nginx

## Requirements
 - [Vagrant](https://www.vagrantup.com/docs/installation/)
 - [Ansible](http://docs.ansible.com/ansible/latest/intro_installation.html)

Ansible is not included in the Vagrant installation, therefore, it has to be installed manually.

## Setup

This Vagrant box is provisioned by an Ansible playbook, but also relies on a certain Ansible role. Before spinning up the container, Ansible depencencies have to be installed:

```
    git clone https://github.com/amuslija/vagrant-ansible-example
    cd vagrant-nginx-example
    ansible-galaxy install -r provisioning/requirements.yaml
```

Once all the dependencies have been installed, simply start the virtual machine from the cloned repository directory:
```
vagrant up
```
Once started and provisioned, the list of system users will be available on `localhost:8080`.
