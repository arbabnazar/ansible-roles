Install Ansible on Mac OSX
----

Ansible uses Python and fortunately Python is already installed on Mac OSX.

###Verify Xcode Installation:

We shall need the developer tools to compile the Ansible, that are the part of Xcode. You can check if the developer tools are running:

```sh
pkgutil --pkg-info=com.apple.pkg.CLTools_Executables
```

If the tools are not installed then, you will see this message:

```sh
No receipt for 'com.apple.pkg.CLTools_Executables' found at '/'.
```

In that case, you can download the Xcode from [here]

Next, Install the Ansible:

```sh
sudo easy_install pip
sudo pip install ansible
```
Later, if you want to update the Ansible, just do:
```sh
sudo pip install ansible --upgrade
```

Ansible also uses the following Python modules:
```sh
sudo pip install paramiko PyYAML jinja2 httplib2
```

###Sample Ansible Hosts File
```ini
[servers]
11.22.33.44 ansible_connection=ssh  ansible_ssh_user=arbab
```
[here]: https://developer.apple.com/xcode
