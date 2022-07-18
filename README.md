# Welcome to my Ansible Inventory

Here we automate the installation of various applications on various operating systems. Commenting this repo is pretty simple. Each directory installs an application on an operating system. 

## Requirements

- A server that you can install and manage Ansible. (My server is Ubuntu Server 20.04 LTS)

You can find the documentation on installing Anible on Ubuntu Server 20.04 LTS [here](https://www.secops.com.tr/tr/ansible/kurulumu).

## Deploying apps with Ansible

After installing Ansible, you must add your servers to the hosts file. If you do not know how to add servers, you will encounter examples in the file.

```
nano /etc/ansible/hosts
```

After adding your servers, go to the folder of the operating system and application you want to install and enter the following command:

- Main file contains other files. If you do not want additional configurations, you should directly type the name of the file you want to run.

```
ansible-playbook main.yml
```

The above command distributes the configuration to all servers in the hosts file. If you don't want this, configure the `/etc/ansible/hosts` file as follows:

```
[servers]
ubuntu-prod ansible_host=10.10.10.102
```

Then just deploy your application in the current directory to the ubuntu-prod machine with the following command:

```
ansible-playbook main.yml --limit ubuntu-prod
```
