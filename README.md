# letsTraefikPortainerPihole
Ansible roles to secure and setup pihole behind a traefik-portainer plus Letsencrypt stack.

# Requiements:
- Configure your ansible controller(IF possible, install using pip for future update):
https://docs.ansible.com/ansible/latest/network/getting_started/basic_concepts.html

- Configure you managed host (check above link)
- Create your vault file:
https://docs.ansible.com/ansible/latest/user_guide/vault.html
- Use Templates to create host_files and vault entries and you're good to go
- Review the inventory file to meet your needs

# Role:
You might use these roles in following order
- check_facts --> Could be used to check if you ansible controller reach corectly your managed host
- servers_update --> Will apply raw update of you newly installed managed host
- preSetupServers --> Will install some tools and dependancies on the managed host (customize depending your needs)
- hardeningServers --> will apply hardening process
- iptables --> will setup traffic filter. Also reveiw it depending you needs
- dockerServerInstall --> Will install docker-ce services on the managed host. Popup traefik-portainer container and link secure access to Letsencrypt
- docker_pihole --> will popup a pihole container

# Playbooks:
Using provided playbook in this order will do the trick
- check_facts_playbook.yml
- updateServers_playbook.yml
- installHardServers_playbook.yml
- dockerServices_playbook.yml
- piHole_playbook.yml
 






