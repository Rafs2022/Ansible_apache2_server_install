# Apache2 server install

This is my Practice Ansible Automation Repo!

I am using a CentOS7 VM and an UBUNTU server VM
for all automated Ansible configurations.

The purpose of this repo is to automate the Apache server installation on 2 Linux distros.

Step 1:

Setup basic inventory file.

added ip addresses of both my VMs

Step 2:

Test connection to VMs

- $ ansible all --key-file ~/.ssh/ansible -i inventory -m ping

- use the -u [username] (for remote connection)

Step 3:

Created ansible.cfg file to define inventory file, and private key location.

Now we can test connection to VMs with:

- $ ansible all -m ping

Step 4:

Created 2 playbooks to Install and Remove apache packages on the Ubuntu Server.

Step 5:

Now lets get the CentOS VM up and running! The 'when' command will help to clean up the automation code. Specifically allowing for agnostic Linux distro automation.

- adding the
  when: ansible_distribution in ["CentOS"]

Step 6:

Lets cleanup the install_apache.yml file even more. We can consolidate installation to just 1 play by using variables and adding "package" as the generic packet-manager module.
