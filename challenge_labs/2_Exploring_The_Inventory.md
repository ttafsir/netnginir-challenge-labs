# Overview: Ansible Inventories
The Ansible inventory is a list of systems from your infrastructure that Ansible can work against. By default, the inventory file is located in `/etc/ansible/hosts`, but you can specify a different path to your inventory file(s) using the `-i` flag at the command line. There are also other options to specify the inventory file (or directory), using environment variables and the ansible configuration files.

## Ansible Inventory Formats
The Ansible inventory may be specified in either the INI or YAML formats.

## Static vs Dynamic Inventories
Static inventories are static files with a list of hosts. Dynamic inventories are generated through scripts. Ansible will, essentially, run an executable scripts that return a list of hosts in a JSON format.

## Documentation
For more documentation about Ansible inventories, visit the [Working with Inventory](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html) page on the [Ansible Documentation](https://docs.ansible.com/) site.

# Labs
## Lab 2.1: Add a host to the default inventory
Login to the control node of your [Vagrant Lab](https://github.com/ttafsir/netnginir-ansible-lab) and add **switch2** to the **eos** group in the default inventory

### Task List
- Vagrant ssh to ctrlnode1
- add **switch2** to the **eos** group
- run the demo playbook in `~/ansible/demo-playbook.yml` using the default inventory file

### Notes
- The login credentials for all systems is: **vagrant/vagrant**
- In order to use **switch2**, make sure that it has been provisioned by Vagrant using `vagrant up switch2`. By default, when you run `vagrant up` only **ctrlnode1** and **switch1** are provisioned. Also, keep in mind that each vEOS instance requires 2048 MB of RAM, so ensure that your system can support running all 3 VMs at the same time.

[View Solution](../solutions/2.1_add_host_to_inventory.md)

## Lab 2.2: change the default inventory
Login to the control node of your [Vagrant Lab](https://github.com/ttafsir/netnginir-ansible-lab) and create new inventory file called `inventory` in `~/ansible`. Create a group called **veos** and add **switch1** to that group. Modify the default ansible configuration file in `/etc/ansible/ansible.cfg` so that your new file is the default inventory. Next, modify the `hosts:` directive in `~/ansible/demo-playbook.yml` to work against your new group. Finally, run  `~/ansible/demo-playbook.yml`.

### Task List
- Vagrant ssh to ctrlnode1
- Create a new inventory file as `~/ansible/inventory` 
- In the new inventory file, create a new group called **veos** and add **switch1** to it
- Modify the default Ansible configuration file `/etc/ansible/ansible.cfg` so that `~/ansible/inventory`  is the new default inventory
- Modify `~/ansible/demo-playbook.yml`
- run the demo playbook in `~/ansible/demo-playbook.yml` using the default inventory file