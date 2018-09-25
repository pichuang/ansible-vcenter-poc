# Ansible Tower PoC for VMware vCenter

The purpose of project are...
1. How to do automated integration with Red Hat Ansible Tower and VMware vCenter
2. Provide sample playbooks based on VMware vCenter API and pyvmomi

## Ansible Playbook Features
- [x] Revert to specific snapshot
- [x] Power on / Shutdown VMs
- [x] Create VM from template
- [x] Change IP per VM

## Ansible Tower Workflow Screenshot

- [x] Workflow 1: Create VM From Template
  - Create VM from template
  - Change IP per VM
- [x] Workflow 2: Revert to specific snapshot
  - Power off VMs
  - Rollback snapshot
  - Powen on VMs

## Validation

```
$ ansible-playbook ping.yml

PLAY [vcenter] ****************************************************************************************************************

TASK [Ping] *******************************************************************************************************************
Tuesday 25 September 2018  22:40:02 +0800 (0:00:00.046)       0:00:00.046 *****
ok: [vcenter.pichuang.local]

PLAY RECAP ********************************************************************************************************************
vcenter.pichuang.local     : ok=1    changed=0    unreachable=0    failed=0

Tuesday 25 September 2018  22:40:03 +0800 (0:00:00.190)       0:00:00.236 *****
===============================================================================
Ping ------------------------------------------------------------------------------------------------------------------- 0.19s
```

## Pre-requisites
- VMware vCenter 6.7
- Red Hat Ansible Tower
- Git Server for version control (e.g GitHub)
- Develop environment for write-up Ansible playbook. Please check the section `Installation` for more detais

## Installation
1. Install Ansible from Red Hat repository
2. Clone repos `git clone https://github.com/pichuang/ansible-vcenter`
3. Install all dependencies by running `pip install -r requirements.txt`
4. Fill out `ansible-vcenter/group_vars/vcenter` includes vcenter_{hostname, username, password, vcenter_dc}
5. (Optional) For security issue, you can encryt the secrect file via `ansible-vault encrypt/decrypt`

## References
- [Using Ansible to manage VMware Infrastructure](https://www.justai.net/en/blog/using-ansible-to-manage-vmware-infrastructure/)
- [GitHub - justai-net/ansible_vmware_snapshot](https://github.com/justai-net/ansible_vmware_snapshot)
