Ansible Role for Scrapy Installation on Ubuntu Server:
---
 This role is helpful to install the Scrapy on Ubuntu server 14.04 LTS.

 [Scrapy Installation Tutorial] - This step by step tutorial explains the manually installation and configuration of Scrapy on Ubuntu server.

### To use this Role:

 Edit the `site.yml` file, mentioned this role:

```yaml
---
- hosts: server
  become: yes
  gather_facts: yes
  roles:
    - scrapy
```

 Then run this command:

```
ansible-playbook -i hosts -u arbab site.yml
```
 **Note:** Please don't forget to change `arbab` with your username
[Scrapy Installation Tutorial]:http://doc.scrapy.org/en/latest/topics/ubuntu.html
