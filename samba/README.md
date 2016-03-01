SAMBA Server Installation on Ubuntu Server using Ansible
--------
There's a blog post that I wrote to go along with this. [Check it out!]

This role is helpful to install SAMBA server on Ubuntu server 14.04 LTS.

[SAMBA Installation Tutorial] - This step by step tutorial explains the installation and configuration of a SAMBA server on Ubuntu server.

### To use this Role:

Edit the `site.yml` file, mentioned this role:

```yaml
---
- hosts: server
  become: yes
  gather_facts: yes
  roles:
    - samba
```
After that edit the `defaults/main.yml` file:

> Change the username(s) and their smbpassword, but these user(s) must exist on the target system.
> Also change the other values as per your requirement. These are self explanatory.

```yaml
---
ubuntu_samba_packages:
  - samba
  - samba-common
  - python-glade2
  - system-config-samba
workgroup: WORKGROUP
public_share_name: public
public_share_path: /samba/public
private_share_name: private
private_share_path: /samba/private
samba_group_name: smbgrp
samba_users:
  - name: 'arbab'
    smbpasswd: 'pass123'
  - name: 'hussain'
    smbpasswd: 'password' 
```

Then run this command:

```
ansible-playbook -i hosts -u arbab site.yml
```
**Note:** Please don't forget to change `arbab` with your username

[SAMBA Installation Tutorial]:https://rbgeek.wordpress.com/2012/04/25/how-to-install-samba-server-on-ubuntu-12-04/
[Check it out!]:https://rbgeek.wordpress.com/2015/02/23/installing-the-samba-server-on-ubuntu-using-ansible/
