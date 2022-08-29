# Ansible

## Install Ansible on local system
    # Ubuntu - sudo apt install ansible

## To check the ansible is connecting to servers or not
    Update the Host file with following Data

    <Public_ip> ansible_ssh_private_key_file=<"file location"> ansible_user=<"username of the mechine">
    
    3.138.186.35 ansible_ssh_private_key_file=/mnt/c/Users/ajay/.ssh/ansible.pem ansible_user=ubuntu
    18.218.191.241 ansible_ssh_private_key_file=/mnt/c/Users/ajay/.ssh/ansible.pem ansible_user=ubuntu

## To check weather the ansible is able to connect to the server mechines or not
    ansible all -i /etc/ansible/hosts -m ping