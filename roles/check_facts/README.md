Role Name
=========

This roles aims to checks facts (it could also be for diagnoses purposes) n ansible managed hosts

Requirements
------------

This role depends on tasks customizations applied using following roles:

- preSetupServers
- hardeningServers
- iptables

Role Variables
--------------

- Define a hosts files
- Define a vault file to protect sensitives properties
- Fill in vault variables

Dependencies
------------
You will need:
- An ansible controller
- Ansible managed hosts
Check this for setup: 
https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

Example Playbook
----------------

Take a look at "check_facts_playbook.yml"

Example Run
-----------
Check all hosts in your inventory:
ansible-playbook "playbook_name" -i inventory -l --ask-vault-pass

Check a specific host in your inventory:
ansible-playbook "playbook_name" -i inventory -l "group or inventory_host depending on your inventory file" --ask-vault-pass

License
-------

BSD

Author Information
------------------
kandji.issa@gmail.com

