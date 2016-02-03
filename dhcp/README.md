DHCP Server Installation on Ubuntu Server using Ansible
--------
This role is helpful to install DHCP server on Ubuntu server 14.04 LTS.

[DHCP Installation Tutorial] - This step by step tutorial explains the installation and configuration of a DHCP server on Ubuntu server.

### To use this Role:

Edit the `site.yml` file, mentioned this role:

```yaml
---
- hosts: server
  become: yes
  gather_facts: yes
  roles:
    - dhcp
``` 
After that edit the `vars/main.yml` file:

> Change these values as per your requirement. These are self explanatory.

```yaml
---
 dhcp_interface: eth0
 subnet_mask: 255.255.255.0
 subnet: 192.168.33 # Please only add the first three octets
 default_gateway: 1 # Please only add the fourth octet i.e: 192.168.33.(1)
 dns_server: 254 # Please only add the fourth octet i.e: 192.168.33.(254)
 domain_name: tendo.local
 start_range: 50 # Start Range Example: 192.168.33.(50)
 end_range: 200  # End Range Example: 192.168.33.(200)
```
Then run this command:

```
ansible-playbook -i hosts -u arbab site.yml
```
**Note:** Please don't forget to change `arbab` with your username

[DHCP Installation Tutorial]:https://rbgeek.wordpress.com/2012/04/29/how-to-install-the-dhcp-server-on-ubuntu-12-04lts/
