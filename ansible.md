## Install Ansible

Dependencies:

    $ sudo apt-get install cdbs sshpass

Now create Ansible DEB package:

    $ git clone git://github.com/ansible/ansible.git
    $ cd ./ansible
    $ git checkout v1.3.3
    $ make deb

DEB package will be located in `../` folder (i.e. one level up)

This steps will allow you to use any version of Ansible on any OS (just checkout to required version)

Now install just created DEB package:

    $ sudo dpkg -i ../ansible_1.3.3_all.deb

Uninstall is as usual:

    $ sudo apt-get remove ansible


## Ansible with sudo users

If you need to specify a password to sudo, run `ansible-playbook` or `ansible` with --ask-sudo-pass (-K). 
If you run a sudo playbook and the playbook seems to hang, it’s probably stuck at the sudo prompt. 
Just Control-C to kill it and run it again with -K.

    ansible all -m ping -u username --sudo -K

If you don't like to type sudo password again and again, give rights to `username` to be a passwordless 
user (see users.md)
