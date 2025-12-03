# Changelog

All notable changes to this project are documented in this file. See
[Conventional Commits](https://conventionalcommits.org) for commit guidelines.

# [1.5.0](https://github.com/ewcloud/ewc-ansible-role-ssh-bastion/compare/1.4.0...1.5.0) (2025-12-03)


### Features

* Automated patch rollout and test automation support ([#4](https://github.com/ewcloud/ewc-ansible-role-ssh-bastion/issues/4)) ([8f93b03](https://github.com/ewcloud/ewc-ansible-role-ssh-bastion/commit/8f93b03b5a0fc75dd6e11756e2a73f1d2a612b3a))

# [1.4.0](https://github.com/ewcloud/ewc-ansible-role-ssh-bastion/compare/1.3.0...1.4.0) (2025-09-22)


### Features

* Fail2Ban input rename for clear user configuration ([#3](https://github.com/ewcloud/ewc-ansible-role-ssh-bastion/issues/3)) ([51cbfe2](https://github.com/ewcloud/ewc-ansible-role-ssh-bastion/commit/51cbfe2bde698baf95c763157291f86941ba111c))

# [1.3.0](https://github.com/ewcloud/ewc-ansible-role-ssh-bastion/compare/1.2.0...1.3.0) (2025-09-05)


### Bug Fixes

* Raise minimum RAM requirement for underlying VM ([85c450e](https://github.com/ewcloud/ewc-ansible-role-ssh-bastion/commit/85c450ed71d15a5ad59b1e21bc57f67addd98b6c))
* Remove VM RAM validation to prevent false positives during role replay ([a943335](https://github.com/ewcloud/ewc-ansible-role-ssh-bastion/commit/a9433352ab8c616ea94b532dfca6a85d0862f435))


### Features

* Disable automatic security patching ([7d6c0f5](https://github.com/ewcloud/ewc-ansible-role-ssh-bastion/commit/7d6c0f55f347413cb0e87eb9d4edbb9e4945e9d3))
* Pin packages versions ([623eb1b](https://github.com/ewcloud/ewc-ansible-role-ssh-bastion/commit/623eb1b7f9489c9c45e98a5fc2a1dfdf8632ea00))
* Restrict supported Linux distros down to the minor version ([db007ef](https://github.com/ewcloud/ewc-ansible-role-ssh-bastion/commit/db007ef4eafdc597785ce59a82a5c97d52845fad))

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
