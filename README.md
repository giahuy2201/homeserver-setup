# Ubuntu Server Ansible
```
ansible-galaxy install -r requirements.yml
```
Put host config file in `host_vars/`

Put `inventory` file here
```
ansible-playbook playbook.yml -i inventory -K
```