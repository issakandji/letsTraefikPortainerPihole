Role Name
=========

docker_pihole behind docker proxy

Requirements
------------
This role depends on tasks customizations applied using following roles:

- preSetupServers
- hardeningServers
- iptables
- dockerServerInstall

Role Variables
--------------

- Define a hosts files
- Fill in vault variables
- Take a look at localdomain.config.yml for pihole specific variables

Dependencies
------------
You will need:
- An ansible controller
- Ansible managed hosts
Check this for setup: 
https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

Example Playbook
----------------

Take a look at "piHole_playbook.yml"

Example Run
-----------
ansible-playbook "playbook_name" -i inventory -l "group or inventory_host depending on your inventory file" --ask-vault-pass -CD

License
-------

BSD

Author Information
------------------
kandji.issa@gmail.com

