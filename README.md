# letsTraefikPortainerPihole
This roles aims to apply iptables rules, fail2ban filters and logs before deploying docker services and bootstrap ecure pihole behind a traefik-portainer-Letsencrypt stack.
It has been successfully run on the following architecture and OS:
Architecture:                    aarch64
CPU op-mode(s):                  32-bit, 64-bit
Byte Order:                      Little Endian
CPU(s):                          4
On-line CPU(s) list:             0-3
Thread(s) per core:              1
Core(s) per socket:              4
Socket(s):                       1
Vendor ID:                       ARM
Model:                           3
Model name:                      Cortex-A72
Stepping:                        r0p3
CPU max MHz:                     1500.0000
CPU min MHz:                     600.0000
BogoMIPS:                        108.00
Vulnerability Itlb multihit:     Not affected
Vulnerability L1tf:              Not affected
Vulnerability Mds:               Not affected
Vulnerability Meltdown:          Not affected
Vulnerability Spec store bypass: Vulnerable
Vulnerability Spectre v1:        Mitigation; __user pointer sanitization
Vulnerability Spectre v2:        Vulnerable
Vulnerability Srbds:             Not affected
Vulnerability Tsx async abort:   Not affected
Flags:                           fp asimd evtstrm crc32 cpuid
###############################################################
ISTRIB_ID=Ubuntu
DISTRIB_RELEASE=20.04
DISTRIB_CODENAME=focal
DISTRIB_DESCRIPTION="Ubuntu 20.04.3 LTS"

# Requiements:
- Configure your ansible controller(I do recommend install using pip for future update):
https://docs.ansible.com/ansible/latest/network/getting_started/basic_concepts.html

- Configure you managed host (check above link)
- Create your vault file:
https://docs.ansible.com/ansible/latest/user_guide/vault.html
- Use Templates to create host_files and vault entries and you're good to go
- Review the inventory file to meet your needs

# Role:
You might use these roles in the following order
- check_facts --> Could be used to check if you ansible controller reach corectly your managed host
- servers_update --> Will apply raw update of you newly installed managed host
- preSetupServers --> Will install some tools and dependancies on the managed host (customize it depending your needs)
- hardeningServers --> will apply hardening process
- iptables --> will setup traffic filter. Also reveiw it depending you needs
- dockerServerInstall --> Will install docker-ce services on the managed host. Popup traefik-portainer container and link secure access to Letsencrypt
- docker_pihole --> will popup a pihole container

# Playbooks:
Using provided playbooks in this order will do the trick
- check_facts_playbook.yml
- updateServers_playbook.yml
- installHardServers_playbook.yml
- dockerServices_playbook.yml
- piHole_playbook.yml
