# Home Server Ansible

## Roles
### 1. System
- `dotfiles.yml`: Git clone dotfiles repo to `$HOME` and create symlinks with *stow*
- `essential.yml`: Update & upgrade packages, check and reboot if needed, set hostname, timezone, swappiness, ipv4.ip_forward
- `networking.yml`: Copy host-specific `$HOSTNAME.interfaces` file and restart/reload networking stack
- `qemu.yml`: Add iommu kernel params, acs override patch, blacklisted devices on host and install guest agent if on VM
- `rpi.yml`: Upgrade EEPROM and set up Ethernet over USB type C for Raspberry Pi
- `serial.yml`: Enable serial console through grub config
- `ssh.yml`: Copy public key, disable password/root login
- `user.yml`: Set user shell, groups and enable passwordless sudo

## Usage

```
ansible-galaxy install -r requirements.yml
```
Put host config file in `host_vars/`

Put `inventory` file here
```
ansible-playbook playbook.yml -i inventory -K
```
with `-e target_host=YOUR_TARGET_HOST` to specify override target, and no need to enter password if the configured user has passwordless sudo access