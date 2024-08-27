---
aliases:
note-type: permanent
date-created: 2024-08-27
long-form-date-created: Tuesday, August 27, 2024
week-created: Week 35.2
time-created: 02:49 PM
---

# Anatomy of a Vagrantfile

Related : [Installing Vagrant](../Book%20Notes%20and%20References%20Library%20📚/DevOps%20for%20the%20Desperate/Installing%20Vagrant.md) - [Vagrant](../3-permanent-notes-🧲/Vagrant.md) - [Ruby Programming Language](Ruby%20Programming%20Language) - [Basic Vagrant Commands](Basic%20Vagrant%20Commands)

A Vagrantfile describes how to build and provision a
[Virtual Machine (VM)](<../3-permanent-notes-🧲/Virtual%20Machine%20(VM).md>).
It's best practice to use ONE, and just only one,
[Vagrantfile](What%20is%20a%20Vagrantfile.md) per project, so one can add the
configuration file to one's project's version control and share it with their team.

The configuration file, Vagrantfile, uses Ruby programming language syntax.

## Basic Principles to Get Started

### Operating System

Vagrant supports multiple [Operating Systems (OS)](../4-hub-notes-🚉/Operating%20Systems.md)
base images, called "boxes", by default. Supported boxes that Vagrant supports
can be found here: <https://portal.cloud.hashicorp.com/vagrant/discover>.

When you find one that you want set that configuration near the top of the
Vagrantfile using the `vm.box` option

```ruby
config.vm.box = "ubuntu/focal64"
```

The `vm.box` identifier is set to `ubuntu/focal64`

### Networking

One can configure the [Virtual Machine (VM)](<../3-permanent-notes-🧲/Virtual%20Machine%20(VM).md>)'s
network options for various network scenarios to define a static IP or
[Dynamic Host Configuration Protocol (DHPC)](<Dynamic%20Host%20Configuration%20Protocol%20(DHPC)>).

This is done via the `vm.network` option near the middle of the file.

```ruby
config.vm.network "private_network", type: "dhcp"
```

The snippet allows the [Virtual Machine (VM)](<../3-permanent-notes-🧲/Virtual%20Machine%20(VM).md>)
to obtain its IP address from a private network using
[Dynamic Host Configuration Protocol (DHPC)](<Dynamic%20Host%20Configuration%20Protocol%20(DHPC)>)

Doing so makes it easy to access resources like a web server on the
[Virtual Machine (VM)](<../3-permanent-notes-🧲/Virtual%20Machine%20(VM).md>)
from the local host.

#### Providers

A "provider" is a plug-in that knows to create and manage a
[Virtual Machine (VM)](<../3-permanent-notes-🧲/Virtual%20Machine%20(VM).md>)
Vagrant supports multiple types of different machines.

Each provider has common options like CPU, disk, and memory.

Vagrant will use the provider's [APIs (Application Programming Interfaces)](<../3-permanent-notes-🧲/APIs%20(Application%20Programming%20Interfaces).md>)
or command line options to create the [Virtual Machine (VM)](<../3-permanent-notes-🧲/Virtual%20Machine%20(VM).md>).
SEE TO: [Basic Vagrant Commands](Basic%20Vagrant%20Commands)

The provider is set near the bottom of the file and looks like the following:

```ruby
config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.name = "dftd"
    vb.customize ["modifyvm", :id, "--uart1", "0x3F8", "4"]
    vb.customize ["modifyvm", :id, "--uartmode1", "file", File::NULL]
end
```

A list of providers can be found here: <https://developer.hashicorp.com/vagrant/docs/providers>

## Sample Vagrantfile

```Ruby
# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "ubuntu/focal64"
  config.vm.hostname = "dftd"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 8888, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network "private_network", type: "dhcp"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.name = "dftd"
    vb.customize ["modifyvm", :id, "--uart1", "0x3F8", "4"]
    vb.customize ["modifyvm", :id, "--uartmode1", "file", File::NULL]
  end

  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "../ansible/site.yml"
    ansible.compatibility_mode = "2.0"
  end
end
```
