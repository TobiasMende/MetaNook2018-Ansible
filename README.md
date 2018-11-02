# MetaNook 2018 Ansible Playbook

## TL;DR

This is a demo Ansible playbook. View the presentation [here](https://tobiasmende.github.io/MetaNook2018-Ansible-Slides/).

## Context

This repository is part of the material I use in my Ansible Session at [MetaNook 2018](https://metanook.de/2018).
Please be aware of the following repositories, as well:

* [RevealJS Slides](https://github.com/TobiasMende/MetaNook2018-Ansible-Slides)
* [Node JS Demo App](https://github.com/TobiasMende/MetaNook2018-Ansible-App)

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