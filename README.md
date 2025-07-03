# EWC Ansible Role SSH Bastion

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
├── ewc-ansible-role-ssh-bastion
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
      ansible_python_interpreter: /usr/bin/bython3
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
| whitelist_ip_ranges | IP ranges (in CIDR format) to be whitelisted in Fail2ban configuration | `list(string)` | `["127.0.0.1/8"]` | yes |

## Final Environment
>⚠️ Versions listed here refer only to those available for RockyLinux 8
packages as of June 26th, 2025. As new security patches/features are 
published by their authors, and newer RockyLinux image versions are 
introduced into the EWC, the effective versions installed in your 
environment might be higher.

Applying this template will trigger the installation of the following 
open-source packages onto your desired target host:

| Name | Version | License | Package Info |
|------|---------|---------|--------------|
| firewalld | >= 0.9.11-9.el8_10 | GPLv2+ | http://www.firewalld.org |
| fail2ban | >= 1.0.2-3.el8 | GPLv2+ | https://www.fail2ban.org |
| dnf-automaitc | >= 4.7.0-20.el8 | GPLv2+ | https://github.com/rpm-software-management/dnf |
| xorg-x11-xauth | >= 1.0.9-12.el8 | MIT | https://www.x.org |

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
