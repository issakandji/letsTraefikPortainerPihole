# letsTraefikPortainerPihole
This roles aims to apply iptables rules, fail2ban filters and logs before deploying docker services and bootstrap ecure pihole behind a traefik-portainer-Letsencrypt stack.
It has been successfully run on the following architecture and OS:
############################################################
<p>Architecture:                    aarch64<br>
CPU op-mode(s):                  32-bit, 64-bit<br>
Byte Order:                      Little Endian<br>
CPU(s):                          4<br>
On-line CPU(s) list:             0-3<br>
Thread(s) per core:              1<br>
Core(s) per socket:              4<br>
Socket(s):                       1<br>
Vendor ID:                       ARM<br>
Model:                           3<br>
Model name:                      Cortex-A72<br>
Stepping:                        r0p3<br>
CPU max MHz:                     1500.0000<br>
CPU min MHz:                     600.0000<br>
BogoMIPS:                        108.00<br>
Vulnerability Itlb multihit:     Not affected<br>
Vulnerability L1tf:              Not affected<br>
Vulnerability Mds:               Not affected<br>
Vulnerability Meltdown:          Not affected<br>
Vulnerability Spec store bypass: Vulnerable<br>
Vulnerability Spectre v1:        Mitigation; __user pointer sanitization<br>
Vulnerability Spectre v2:        Vulnerable<br>
Vulnerability Srbds:             Not affected<br>
Vulnerability Tsx async abort:   Not affected<br>
Flags:                           fp asimd evtstrm crc32 cpuid</p>
###############################################################
<p>ISTRIB_ID=Ubuntu<br>
DISTRIB_RELEASE=20.04<br>
DISTRIB_CODENAME=focal<br>
DISTRIB_DESCRIPTION="Ubuntu 20.04.3 LTS"<p>

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

# To-Do:
- [x] DoT
- [ ] Test DoH
- [ ] More docker service security related
- [ ] Backup ? 


<p>@pihole/Thanks for making it possible<br>
@tecnativa/Thanks for making docker service more secure<p>