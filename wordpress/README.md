Wordpress Installation on Ubuntu Server using Ansible
--------
There's a blog post that I wrote to go along with this. [Check it out!]

This role is helpful to install the Wordpess with LEMP stack on Ubuntu server 14.04 LTS.

[Wordpress Installation Tutorial] - This step by step tutorial explains the installation and configuration of Wordpress on Ubuntu server.

### Dependencies:

This role is depend on the LEMP Stack role, which is also available in the ansible-roles repo.

### To use this Role:

Edit the `site.yml` file, mentioned this role:

```yaml
---
 - hosts: server
   sudo: True
   gather_facts: True
   roles:
     - wordpress
``` 

After that edit the `vars/main.yml` file:

> Change these values as per your requirement. These are self explanatory.

```yaml
---
 website_name: rbgeek.com
 wordpress_dir: /var/www
 wordpress_url: http://wordpress.org/latest.tar.gz
 wordpress_user: rbgeek_user
 wordpress_passwd: wordpress_password
 wordpress_db: rbgeek_database
```

Then run this command:

```
ansible-playbook -i hosts -u arbab site.yml
```
**Note:** Please don't forget to change `arbab` with your username

[Wordpress Installation Tutorial]:https://rbgeek.wordpress.com/2014/06/26/how-to-install-wordpress-with-nginx-in-ubuntu-server-14-04-lts
[Check it out!]:https://rbgeek.wordpress.com/2015/02/25/installing-the-wordpress-on-ubuntu-using-ansible/
