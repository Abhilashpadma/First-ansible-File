# First-ansible-File
First Ansible Script
---
- name: Install and start ngnix
  hosts: all
  become: root

  tasks:
   - name: Install ngnix
     apt:
       name: ngnix
       state: present
   - name: Start ngnix
     service:
       name: ngnix
       state: started

# Explanation

Here first we write ansible files in yaml
The start of yaml file indicate this 3 "---"
the next line we write is the list of playbooks
like the first one the name and what hosts you want to execute and here become is like we should take root or user

and below that we need to write all the task 
here we are using apt module of ansible to install ngnix

and service module to run the ngnix image

## Commands to execute once we write the file
1) ansible-playbook -i <inventory_filename or path> <playbook_filename>

### To get the logs of the file while executing it, like in detail what ansible is doing while executing the file. we use the verbose it is command we get the logs of 
1) ansible-playbook -v -i inventory first-playbook.yaml
here -v like it give minimum logs
2)ansible-playbook -v -i inventory first-playbook.yaml
here -vv means it gives in more details
like if we increase more v's it gives more in detail.

