# Introduction
This repository contains the ansible setup for my personal workspace(s).

# Getting started
1. Ensure that the host you want to update is accessible from ssh
2. Complete the `Setting up ssh` steps below
3. Update the inventory.yaml file to add necessary hosts
4. Ensure all hosts are accessible: `ansible myhosts -m ping -i inventory.yaml`
5. Run the test playbook: `ansible-playbook -i inventory.yaml playbooks/hello-world.yaml`

# Setting up ssh
1. Make sure your localhost has a ssh key that gets used (check the ~/.ssh directory for a file like `id_ed25519`)
2. Copy the pub file to the remote host `scp ~/.ssh/id_ed25519.pub user@remote-host:~/.ssh/authorized_keys`
3. Confirm the `authorized_keys` has chmod `600`

# Running playbooks
## Install system
```
ansible-playbook -i inventory.yaml --ask-become-pass playbooks/install-packages.yaml
```
## Install config
```
ansible-playbook -i inventory.yaml playbooks/install-config.yaml
```

# TODO
- add ability to detect between ubuntu and arch system
- set up configuration files for various services (like i3, neovim etc)




