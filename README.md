[![Build Status](https://img.shields.io/travis/ptavares/ansible-role-terraform/master.svg?style=flat-square)](https://travis-ci.org/ptavares/ansible-role-terraform)
[![Ansible Role](https://img.shields.io/ansible/role/29415.svg)](https://galaxy.ansible.com/ptavares/ansible-role-terraform)
[![License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](https://github.com/ptavares/ansible-role-terraform/blob/master/LICENSE)

ansible-role-terraform
=========

Ansible role for installating Terraform executable

Requirements
------------

Only test with ansible 2.5 min version

Role Variables
--------------
Available variables are listed below, along with default values (see [defaults/main.yml](https://github.com/ptavares/ansible-role-terraform/blob/master/defaults/main.yml)):

### Terraform version 

```yaml
# By default, module will download last version
# To specify a version, use this below param
terraform_install_version: X.X.X
```
### Download information

```yaml
# Directory where zip will be downloaded before installation
terraform_download_location: /tmp/
# Url to terraform zip
terraform_url: "https://releases.hashicorp.com/terraform/{{ terraform_install_version | regex_replace('^v', '') }}/terraform_{{ terraform_install_version | regex_replace('^v', '') }}_linux_amd64.zip"
# Downloaded file name
terraform_downloaded_file_name: "terraform_{{ terraform_install_version | regex_replace('^v', '') }}_linux_amd64.zip"
```

### Installation information

```yaml
# Path where to install terraform
terraform_execution_path: /usr/local/bin
# Execution file name for terraform
terraform_execution_file_name: terraform
```

Dependencies
------------

No dependencie

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: ptavares.ansible_role_terraform
```
Inside *`vars/main.yml`*:
- Copy content of [defaults/main.yml](https://github.com/ptavares/ansible-role-terraform/blob/master/defaults/main.yml) in your playbook's vars file if needed.
- Customize it as you like (filling role's variables)

License
-------

MIT
