VNC Server Installation on Ubuntu Server using Ansible
--------
There's a blog post that I wrote to go along with this. [Check it out!]

This role is helpful to install VNC server on Ubuntu server 14.04 LTS.

[VNC Installation Tutorial] - This step by step tutorial explains the installation and configuration of a VNC server on Ubuntu server.

### To use this Role:

Edit the `site.yml` file, mentioned this role:

```yaml
---
 - hosts: vncserver
   become: yes
   gather_facts: yes
   roles:
     - vnc
``` 
After that edit the `defaults/main.yml` file:

> Change the username(s),port(s) and resolution for VNC Client as per your environment, but these user(s) must exist on the target system.
> Here 1 will make vnc port 5901 for the user, 2 will enable the user to get access to the VNC Server with the port 5902.
> Don't forget to change the password because it will be used by the user to login to the VNC Server.


Then run this command:

```
ansible-playbook -i hosts -u arbab site.yml
```
**Note:** Please don't forget to change `arbab` with your username

[VNC Installation Tutorial]:https://rbgeek.wordpress.com/2012/06/25/how-to-install-vnc-server-on-ubuntu-server-12-04/
[Check it out!]:https://rbgeek.wordpress.com/2015/03/18/installing-the-vnc-server-on-ubuntu-using-ansible/
