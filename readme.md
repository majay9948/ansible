# Ansible

## Install Ansible on local system
    Ubuntu - sudo apt install ansible

## To check the ansible is connecting to servers or not
    Update the Host file with following Data

    <Public_ip> ansible_ssh_private_key_file=<"private_key_ssh_file_location"> ansible_user=<"username of the mechine">
    
    3.138.186.35 ansible_ssh_private_key_file=/mnt/c/Users/ajay/.ssh/ansible.pem ansible_user=ubuntu
    18.218.191.241 ansible_ssh_private_key_file=/mnt/c/Users/ajay/.ssh/ansible.pem ansible_user=ubuntu

## To check weather the ansible is able to connect to the server mechines or not
    ansible <group or all or single host> -i <host_file_location> -m <module_name>
    ansible all -i /etc/ansible/hosts -m ping

## To configue 50 servers with same ssh key and same username 
    in the host file we need to group them

    [aws]
    <server_1_ip>
    <server_2_ip>
    <server_3_ip>
    <server_4_ip>
        ....
    <server_50_ip>

    [aws:vars]
    ansible_ssh_private_key_file=/mnt/c/Users/ajay/.ssh/ansible.pem
    ansible_user=ubuntu

    to configure the aws group mechines file 

    ansible aws -i /etc/ansible/hosts -m ping