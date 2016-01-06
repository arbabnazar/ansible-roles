Create Linux User(s) with github key
=========

This role manage(either create or delete) the user(s) with github users' ssh keys.

To use this Role:
--------------

Edit the `site.yml` file, mentioned this role:
```
---
 - hosts: server
   sudo: True
   gather_facts: True
   roles:
     - users-with-github-key
```

After that edit the `defaults/main.yml` file:

Change the username(s), type(either admin/sudo user or not) and state of the user(want to create or remove it on the target system). These are self explanatory.

```
 users_list:
  - username: arbabnazar
    type: admin
    state: present
  - username: rbgeek
    type: admin
    state: present
  - username: tendo
    type: normal
    state: absent
```
Then run this command:
```
ansible-playbook -i hosts -u arbab site.yml
```
**Note:**Please don't forget to change arbab with your username
