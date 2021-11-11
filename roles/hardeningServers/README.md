Role Name
=========

This roles aims to secure the server before hosting a pihole behind traefik portainer using Letsencrypt Certificates.
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

Requirements
------------
This role depends on tasks customizations applied using following roles:

- preSetupServers

Role Variables
--------------

- Define a hosts files
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

Take a look at "installHardServers_playbook.yml"

Example Run
-----------
ansible-playbook "playbook_name" -i inventory -l "group or inventory_host depending on your inventory file" --ask-vault-pass -CD

License
-------

BSD

Author Information
------------------
kandji.issa@gmail.com

