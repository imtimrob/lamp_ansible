# lamp_ansible

This will setup a new ubuntu/focal64 VM via Vagrant/Virtualbox.
*Requires Virtualbox and Vagrant installed. 
*Install Ansible in Python Virtual environment as follows

https://www.virtualbox.org

https://www.vagrantup.com

## TODO
* Add specific files for an Apache hosted website via ansible
* Add Secure Mysql configuration via ansible




Once you have repository cloned locally:

1. Create a Python virtual environment
  
    python3 -m venv venv
    
2. Activate the virtual environment

    . venv/bin/activate
    
3. upgrade pip 

    pip install -U pip wheel
    
4. Install Ansible with pip

    pip install ansible
    
5. Edit ansible.cfg
    
    change line "private_key_file =" with path to keyfile
    on mac you probably only need to change the username /Users/$userName/.vagrant.d/insecure_private_key
    
    * Key should to be converted to a secure ssh key, but this is fine for development


6. Start Vagrant

    vagrant up
    
    This will automatically download vagrant box ubuntu/focal64 which might take a while.
    After it finishes the box will always be available for new vms
    
vagrant.yml is the main provision file for ansible.

This will install some basic utilities, then install PHP Apache2 and Mysql
when it finishes point a browser at http://localhost:8080

7. login with vagrant ssh
    
8. secure mysql

    mysql_secure_installation
    
    * planning to add this step to ansible


From there the vagrant.yml file can be edited with additional packages and configurations.
If you want to use seperate .yml files for each configuration, just add 'import fileName.yml'
to the end of 'vagrant.yml'.

Then use 'vagrant provision' for running containers
