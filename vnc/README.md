VNC Server Installation on Ubuntu Server using Ansible
--------
This role is helpful to install VNC server on Ubuntu server 14.04 LTS.

[VNC Installation Tutorial] - This step by step tutorial explains the installation and configuration of a VNC server on Ubuntu server.

### To use this Role:

Edit the `site.yml` file, mentioned this role:

```yaml
---
 - hosts: vncserver
   sudo: True
   gather_facts: True
   roles:
     - vnc
``` 
After that edit the `vars/main.yml` file:

> Change the username(s),port(s) and resolution for VNC Client as per your environment, but they should exist on the target system.
> Here 1 will make vnc port 5901 for the user, 2 will enable the user to get access to the VNC Server with the port 5902.
> Don't forget to change the password becasue it will be used by the user to login to the VNC Server.


Then run this command:

```
ansible-playbook -i hosts -u arbab site.yml
```
**Note:** Please don't forget to change `arbab` with your username

[VNC Installation Tutorial]:https://rbgeek.wordpress.com/2012/06/25/how-to-install-vnc-server-on-ubuntu-server-12-04/
