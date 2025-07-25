# SSH Bastion Ansible Role

This repository contains a configuration template 
(i.e. an [Ansible Role](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_reuse_roles.html)) 
to customize your environment in the
[European Weather Cloud (EWC)](https://europeanweather.cloud/).
The template is designed to:
* Configure pre-existing RockyLinux 8 or RockyLinux 9 virtual machines (with 
public IP address), as entrypoint for users who wish to reach private
EWC networks from the public internet via SSH.

## Copyright and License
>💡 No dependencies are distributed as part of this repository.

See the [LICENSE](./LICENSE) file for licensing information as it pertains to
files in this repository.

## Usage

The step-by-step described below assume your local file system follows the 
example structure below, with `ewc-ansible-role-ssh-bastion` being a clone of this
repository:
```
.
├── roles
│   └── ewc-ansible-role-ssh-bastion
├── inventory.yml
└── playbook.yml
```

### 1. Specify the target host and SSH credentials
Create an inventory file to specify address/credentials that Ansible should use
to reach the virtual machine you wish to configure:
```yaml
# inventory.yml
---
ewcloud:
  hosts:
    ssh_bastion:
      ansible_python_interpreter: /usr/bin/python3
      ansible_host: <add the IPV4 address of the target host>
      ansible_ssh_private_key_file: <add the path to local SSH RSA private key file>
      ansible_user: <add the username which owns the SSH RSA private key >
```
### 2. Customize the template

Edit input values for the template [variables](./vars/main.yml) as needed (see
[Inputs](#inputs) section for details).
Then, proceed to create an Ansible Playbook file to load your customizations: 

```yaml
# playbook.yml
---
- name: SSH Bastion Library Item Automation Script
  hosts: ssh_bastion
  become: true
  become_user: root
  become_method: ansible.builtin.sudo

  roles:
    - ewc-ansible-role-ssh-bastion
```

### 3. Apply the template


You can apply changes on the target host by running:
```bash
ansible-playbook -i inventory.yml playbook.yml
```

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| whitelist_ip_ranges | IPv4 ranges (in CIDR format) to be whitelisted in Fail2ban configuration. Example: `['10.0.0.0/24']` | `list(string)` | n/a | no |

## Final Environment

### RockyLinux 8 Environment

Applying this template will trigger the installation of the following 
open-source packages onto your desired target RockyLinux 8 host:

| Name | Version | License | Package Info |
|------|---------|---------|--------------|
| firewalld | 0.9 | GPLv2+ | http://www.firewalld.org |
| fail2ban | 1.0 | GPLv2+ | https://www.fail2ban.org |
| xorg-x11-xauth | 1.0 | MIT | https://www.x.org |

### RockyLinux 9 Environment

Likewise, on your desired target RockyLinux9 host, the template will trigger installation of the following open-source packages:

| Name | Version | License | Package Info |
|------|---------|---------|--------------|
| firewalld | 1.3 | GPLv2+ | http://www.firewalld.org |
| fail2ban | 1.0 | GPLv2+ | https://www.fail2ban.org |
| xorg-x11-xauth | 1.1 | MIT | https://www.x.org |

## Changelog
All notable changes (i.e. fixes, features and breaking changes) are documented 
in the [CHANGELOG.md](./CHANGELOG.md).

## Contributing

Thanks for taking the time to join our community and start contributing!
Please make sure to:
* Familiarize yourself with our [Code of Conduct](./CODE_OF_CONDUCT.md) before 
contributing.
* See [CONTRIBUTING.md](./CONTRIBUTING.md) for instructions on how to request 
or submit changes.

## Authors

[European Weather Cloud](http://support.europeanweather.cloud/) 
<[support@europeanweather.cloud](mailto:support@europeanweather.cloud)>
