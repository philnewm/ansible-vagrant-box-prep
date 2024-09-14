## Vagrant Box Prep

[![Alma9-CI](https://github.com/philnewm/ansible-vagrant-box-prep/actions/workflows/alma9-ci.yml/badge.svg)](https://github.com/philnewm/ansible-vagrant-box-prep/actions/workflows/alma9-ci.yml) [![Rocky9-CI](https://github.com/philnewm/ansible-vagrant-box-prep/actions/workflows/rocky9-ci.yml/badge.svg)](https://github.com/philnewm/ansible-vagrant-box-prep/actions/workflows/rocky9-ci.yml) [![CentOS9-CI](https://github.com/philnewm/ansible-vagrant-box-prep/actions/workflows/centos9-ci.yml/badge.svg)](https://github.com/philnewm/ansible-vagrant-box-prep/actions/workflows/centos9-ci.yml) [![Debian12-CI](https://github.com/philnewm/ansible-vagrant-box-prep/actions/workflows/debian12-ci.yml/badge.svg)](https://github.com/philnewm/ansible-vagrant-box-prep/actions/workflows/debian12-ci.yml) [![Ubuntu22.04-CI](https://github.com/philnewm/ansible-vagrant-box-prep/actions/workflows/ubuntu2204-ci.yml/badge.svg)](https://github.com/philnewm/ansible-vagrant-box-prep/actions/workflows/ubuntu2204-ci.yml)

Runs a bunch of small tasks to prepare a vagrant box which uses the provider virualbox.



This role includes a full vagrant based molecule testing setup at `extensions/molecule/default`

# Structure

```
📦 ansible-vagrant-box-prep
 ┣ 📂 defaults
 ┃ ┗ 📜 main.yml
 ┣ 📂 meta
 ┃ ┗ 📜 main.yml
 ┣ 📂 molecule
 ┃ ┗ 📂 default
 ┃   ┗ 📜, 📜, 📜, scenario_files
 ┣ 📂 tasks
 ┃ ┣ 📜 main.yml
 ┃ ┣ 📜 present.yml
 ┃ ┣ 📜 dependencies.yml
 ┃ ┣ 📜 absent.yml
 ┃ ┗ 📜 init.yml
 ┣ 📂 templates
 ┃ ┗ ⛩️ ubuntu_netplan_config.j2
 ┗ 🗒️ README.md
 ┗ 📓 requirements.txt

```

Describe and explain role structure. 

## Role Variables

* defaults/main.yml
  * initial_netplan_config_path: default netplan config
  * expected_net_plan_config_path: Adjusted netplan config
  * python_selinux: python se-linux package name depening on OS family
  * nfs_package: nfs package name depening on OS family


## Dependencies

This role doesn't depend on any additional ansible-galaxy roles.

## Example Playbook

Add an example playbook
```yaml
---

tasks:
  - name: Include ansible-vagrant-box-prep present
    ansible.builtin.include_role:
      name: ansible-vagrant-box-prep
    vars:
      ansible_vagrant_box_prep_state: present

...
```
## License

MIT
