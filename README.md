# Ansible Demo for MetaNook 2018

## How to setup

Vagrant is used for demonstration puposed. Thus run `vagrant up` to spin up the infrastructure.

## Install Playbook Dependencies

Run `ansible-galaxy install -r requirements.yml` in this directory.

## Run Ansible

In order to run Ansible against the vagrant infrastructure, run `ansible-playbook site.yml -i vagrant.ini --ask-vault-pass`.
The vault password is `fish123`. ;-)

## Ansible Vault

For explanatory purposes, the file `group_vars/all` is an encrypted vault file.
It can be decrypted/encrypted using `ansible-vault` and the vault password above:
- `ansible-vault decrypt --ask-vault-pass group_vars/all`
- `ansible-vault encrypt --ask-vault-pass group_vars/all`

The file is modified in place by these commands.

## Requirements
- Vagrant (+ VirtualBox)
- Vagrant Landrush (`vagrant plugin install landrush`)
- Ansible