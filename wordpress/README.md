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
- hosts: all
  become: yes
  gather_facts: yes
  roles:
    - wordpress
``` 

After that edit the `defaults/main.yml` file:

> Change these values as per your requirement. These are self explanatory.

```yaml
---
mysql_port: 3306 #Default is 3306, please change it if you are using non-standard
mysql_bind_address: "127.0.0.1" #Change it to "0.0.0.0",if you want to listen everywhere
mysql_root_pass: mypassword #MySQL Root Password
connections: 1024 #Nginx Connection

website_name: test.com
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
