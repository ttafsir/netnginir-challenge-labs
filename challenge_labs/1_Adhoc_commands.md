# Overview: Ad-hoc commands
Ansible can be run in either an ad-hoc mode or using playbooks. Ad-hoc mode allows you to perform tasks as one-liners by giving the capability to run a module against a host (or group of hosts).

## Ad-hoc Uses Cases
### Operational
* check device logs
* stop/start services
* check processes across groups of hosts (routing process)

### Informational
* check OS versions
* check devices properties (show version)
* gather system performance (CPU, memory use)

### Research/practice
* test new modules on test systems

## Documentation
For more documentation on Ad-hoc commands visit the [Introduction To Ad-Hoc Commands](https://docs.ansible.com/ansible/latest/user_guide/intro_adhoc.html) page on the [Ansible Documentation](https://docs.ansible.com/) site.

# Labs
## Lab 1.1: Get information from network device
login to the control node of your [Vagrant Lab](https://github.com/ttafsir/netnginir-ansible-lab) and run an ad-hoc command to get the output of `show version` from the devices in the eos group. Be sure to supply the SSH password at the CLI.

### Task List:
- Vagrant ssh to ctrlnode1
- change into the 'ansible' directory
- run adhoc command

[View Solution](../solutions/1.1_adhoc_commands.md)