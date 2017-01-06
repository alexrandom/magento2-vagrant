# Vagrant for Magento2

## Prerequisites
### Virtualbox
[VirtualBox](https://www.virtualbox.org/) is an open source virtualizer, an application that can run an entire operating system within its own virtual machine. 

1. Download the installer for your operating system using the link below.
    * [VirtualBox download](https://www.virtualbox.org/wiki/Downloads)
1. Run the installer, choosing all of the default options.
    * Windows: Grant the installer access every time you receive a security prompt.
    * Mac: Enter your admin password.
    * Linux: Enter your root password if prompted.
1. Reboot your system if prompted to do so when installation completes.
1. Close the VirtualBox window if it pops up at the end of the install.

### Vagrant
[Vagrant](https://www.vagrantup.com/) is an open source command line utility for managing reproducible developer environments. 

1. Download the installer for your operating system using the link below.
    * [Vagrant download](https://www.vagrantup.com/downloads.html)
1. Run the installer, choosing all defaults.
1. Reboot your system if prompted to do so when installation completes.

## Usage
After Vagrant and Virtualbox are setup, run the following commands to install the Dev Box. 

**Clone the Repository**

    git clone https://github.com/alexrandom/magento2-vagrant.git

**Add Magento Repository Access keys**

Read [this](http://devdocs.magento.com/guides/v2.1/install-gde/prereq/connect-auth.html) guide to get a personal access keys.  Once you have created the authentication keys, open up the `Vagrantfile` and place the keys here:

    mageRepoPublicKey = ""
    mageRepoPrivateKey = ""
_Note: If you did not enter a personal access keys, Composer will not run automatically.  You will have to install Magento 2 yourself to finish installation._

**Run Vagrant Command**

    vagrant up

The configuration process will take a while, especially if it is the first time you use a vagrant box with this virtual machine, because this one had to be completely downloaded at the first utilization.

Once completed, you can connect via SSH to your virtual machine, with putty for example. The address and the port are usually
127.0.0.1 and 2222 respectively, but it can change if you have many VMs running at the same time.

**Magento 2 Access**
Once your VM is running, Magento 2 should be accessible from http://192.168.33.10/
Admin panel:

    Host: http://192.168.33.10/admin
    Login: admin
    Password: password1

**Other Info**

    Database Username: root
    Database Password: (none)
    SSH Login : vagrant
    SSH Password : vagrant
    root user password: vagrant
    Database Name: magento
    URL of Instance: http://192.168.33.10/
    Host File Configuration: 192.168.33.10 www.magento2.dev magento2.dev
