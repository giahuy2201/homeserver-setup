# Ubuntu Server Ansible
```
ansible-galaxy install -r requirements.yml
```
Put host config file in `host_vars/`

Put `inventory` file here
```
ansible-playbook playbook.yml -i inventory -K
```
with `-e target_host=YOUR_TARGET_HOST` to specify override target, and no need to enter password if the configured user has passwordless sudo access