# connect-fw-to-cdl
Ansible script to run a few commands needed to connect panos firewalls to CDL.

### REQUIRES
* ansible (v 2.9) (sudo apt-add-respository --yes ppa:ansible/ansible ; sudo apt update ; sudo apt install ansible)
* palo role (sudo ansible-galaxy collection install paloaltonetworks.panos)
* python (tested with version 2.7.12)
* python pip (tested with version 8.1.1 for 2.7) 
* pandevice python package (sudo -H pip install pandevice)
 

### STEPS
* update `vars.yml` with valid user/password
* update `hosts` with list of firewall ip addresses
* update *ansible_python_interpreter* in the playbook with correctlocation of python
* Note: you must make sure outside of this playbook that there is a CDL license on the firewall to delete
* Since Panorama is used, this can be configured in **Panorama -> Device Deployment -> Licenses** ; then **Refresh**

### EXECUTE
```
ansible-playbook -i hosts connect-fw-to-cdl.yml
```

_This code is my own. Provided without warranty or affilitation with Palo Alto Networks._
