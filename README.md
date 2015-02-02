Ansible Roles:
=============

 This repo contains all the Ansible roles that I've written to perform my day-to-day system administration and automation tasks.

 **Note:** Be very careful to run these roles directly to the Production, please first try them on the Testing Environment before using them to Production.

### Requirements:


We need Ansible software to be installed in order to use these roles, mean Roles can be run from any machine that have Ansible installed on.

Here's the steps to install the Ansible on Ubuntu 14.04 LTS:
```
sudo apt-add-repository -y ppa:ansible/ansible
sudo apt-get update
sudo apt-get install -y ansible
```

### To use any Role:

Edit the `site.yml` file, mentioned the role that you want to use and then run this command:
```
ansible-playbook -i hosts site.yml
```