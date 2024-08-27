---
date-created: 2024-08-20
long-form-date-created: Tuesday, August 20, 2024
week-created: Week 34.2
time-created: 11:25 AM
---

# Vagrant

Related : [Ansible](Ansible.md), [Infrastructure as Code (IaC)](<Infrastructure%20as%20Code%20(IaC).md>), [Vagrant and Ansible](../Book%20Notes%20and%20References%20Library%20📚/DevOps%20for%20the%20Desperate/Vagrant%20and%20Ansible.md)

Topics : [DevOps](DevOps)

Is a framework that automates the process of creating and managing [Virtual Machines (VM)](<../3-permanent-notes-🧲/Virtual%20Machine%20(VM).md>)
and supports multiple [Operating Systems](../4-hub-notes-🚉/Operating%20Systems.md)
across various platforms.

A "Vagrantfile" is the single framework specific configuration file that
describes the virtual environment in one's code used to create the local
infrastructure.

## Installation

Prerequisite: Make sure that your VirtualBox has "guest additions" installed on
it. "Guest additions" provide better driver support, port forwarding, and have
more options available.

1. Download: <https://developer.hashicorp.com/vagrant/install>
2. Enter the following command in the terminal to install Vagrant plug-in for guest additions
   1. `vagrant plugin install vagrant-vbguest`

It is good practice to update this plug-in anytime you upgrade Vagrant and VirtualBox.
