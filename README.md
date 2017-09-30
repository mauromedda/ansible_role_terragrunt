ansible_role_terragrunt
======================

This is a simple ansible role to install terragrunt into a RedHat-like 7+ box.


Requirements
------------

This module hasn't specific requirements just Ansible.

Role Variables
--------------

```yaml
terragrunt_version: 0.13.5
```
 * terragrunt_version: Specify the terragrunt version to install

```yaml
terragrunt_dist_file: "terragrunt_{{terragrunt_version}}_linux_amd64.zip"
```
 * terragrunt_dist_file: Terraform distribution archive

```yaml
terragrunt_repo_url: "https://releases.hashicorp.com/terragrunt/{{terragrunt_version}}/{{ terragrunt_dist_file }}"
```
 * terragrunt_repo_url: Terraform distribution URL. Used to fetch the Terraform binary

```yaml
terragrunt_base_install_dir: /opt/hashicorp/terragrunt
```

 * terragrunt_base_install_dir: Root of the Terraform installation

```yaml
terragrunt_bin: /usr/bin/terragrunt
```
 * terragrunt_bin: Terraform binary location

```yaml
terragrunt_requirements:
  - unzip
```

 * terragrunt_requirements: Terraform playbook requirements

```yaml
terragrunt_purge_old: true
```

 * terragrunt_purge_old: Delete the oldest version installed in the system. Default: true

```yaml
terragrunt_cleanup: true
```
 * terragrunt_cleanup: Remove the Terraform distribution archive. Default: true



Example Playbook
----------------

```yaml
---
- hosts: localhost
  become: true
  connection: local

  roles:
    - mauromedda.ansible_role_unzip
    - mauromedda.ansible_role_terraform
    - mauromedda.ansible_role_terragrunt
```

License
-------

BSD

Author Information
------------------

Author: Mauro Medda 
