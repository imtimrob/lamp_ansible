# lamp_ansible
#
# TODO
# Add Files for Apache website
# Add Secure Mysql configuration via ansible

*Requires Virtualbox and Vagrant installed then install Ansible in Python Virtual environment as follows

Once you have repository cloned locally:

1. Create a Python virtual environment
  
    python3 -m venv venv
    
2. Activate the virtual environment

    . venv/bin/activate
    
3. upgrade pip 

    pip install -U pip
    
4. Install Ansible with pip

    pip install ansible
    
5. Edit ansible.cfg
    
    change line "private_key_file =" with path to keyfile
    on mac you probably only need to change the username /Users/$userName/.vagrant.d/insecure_private_key
    
    * This needs to be converted to a secure ssh key, but this is fine for development


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
