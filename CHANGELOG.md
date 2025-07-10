# Changelog

All notable changes to this project are documented in this file. See
[Conventional Commits](https://conventionalcommits.org) for commit guidelines.

# [1.2.0](https://gitlab.eumetsat.int/HP-EWC/ewc-community-hub/ewcloud/ewc-ansible-role-ssh-bastion/compare/1.1.0...1.2.0) (2025-07-10)


### Features

* Set input values as optional ([e47abab](https://gitlab.eumetsat.int/HP-EWC/ewc-community-hub/ewcloud/ewc-ansible-role-ssh-bastion/commit/e47abab940963cd17c2a389775507462b5cb115c))

## [1.1.0](https://gitlab.eumetsat.int/HP-EWC/ewc-community-hub/ewcloud/ewc-ansible-role-ssh-bastion/compare/1.0.0...1.1.0) (2025-07-03)

### Features

* Enforce input type and add input validation ([85517cd](https://gitlab.eumetsat.int/HP-EWC/ewc-community-hub/ewcloud/ewc-ansible-role-ssh-bastion/commit/85517cdb63e97162f639e1cc269d2ad6b17e5b19))

## 1.0.0 (2025-06-27)

### Features

* Automatic security patch rollout via built-in RockyLinux functionality ([1d9c3c2](https://gitlab.eumetsat.int/HP-EWC/ewc-community-hub/ewcloud/ewc-ansible-role-ssh-bastion/commit/1d9c3c209624b9d158d179bf4ba1398a06f405be))
* Configured Fail2ban SSH jail for brute-forced access protection ([c5b9ed1](https://gitlab.eumetsat.int/HP-EWC/ewc-community-hub/ewcloud/ewc-ansible-role-ssh-bastion/commit/c5b9ed1f0d384ff69fab4f4fce12c6b2dd717407))
* Disabled root SSH access to reduce attack surface ([74d0d2c](https://gitlab.eumetsat.int/HP-EWC/ewc-community-hub/ewcloud/ewc-ansible-role-ssh-bastion/commit/74d0d2c55af0f1c8a89f00d78b73a6a7e5d18f6e))
* Ensure configured services stay operational between VM reboots ([ad4ba95](https://gitlab.eumetsat.int/HP-EWC/ewc-community-hub/ewcloud/ewc-ansible-role-ssh-bastion/commit/ad4ba957bc495df00c0007eb301c6338aea074c1))
* Install and list versions of core requirements and extra fail2ban package ([04afcdd](https://gitlab.eumetsat.int/HP-EWC/ewc-community-hub/ewcloud/ewc-ansible-role-ssh-bastion/commit/04afcdd84ea855d4058ea938d3e0adba5653bf3f))
* Linux distro check to ensure deployment on RockyLinux 8 and 9 only ([e351361](https://gitlab.eumetsat.int/HP-EWC/ewc-community-hub/ewcloud/ewc-ansible-role-ssh-bastion/commit/e351361fb95334ce322f6ae7fd2de9cc21920043))
