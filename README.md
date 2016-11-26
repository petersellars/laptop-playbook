# Machine Playbook
This repository contains an [Ansible][1] playbook used to both experiment and learn about Ansible
playbooks. It is intended for experimenting with building, testing, running and maintaining playbooks.

This playbook is going to be used to provision and maintain my personal development machines. It will
evolve over time and is likely to be only applicable to me! As a playbook though it should be useful
for configuration management contributors as a reference in building playbooks. I plan to use this as
a stepping stone to Ansible module creation. 

## Pre-Commit
This repository utilises [pre-commit][2] to run [ansible-lint][3]. Pre-commit aims to reduce the pain
of using pre commit hooks across projects. Pre-commit uses the [./pre-commit-config.yaml] file to
configure pre-commit plugins.

To install pre-commit into your git hooks run `pre-commit install`. You should run `pre-commit install`
whenever you clone this project.  

Currently this repository uses the following pre-commit hook:
* [ansible-lint][3]

## Install requirements from Ansible Galaxy
```sudo ansible-galaxy install -r requirements.yml```

## Running this playbook
The playbook utilises the `become: true` escalated privilege and is run using a user in the `sudo`
group that does not have to enter a password. 

```ansible-playbook -i "localhost,", -c local machine.yml```

## TO-DO
* Create [Vagrant](https://vagrantup.com) machine to test the playbook

[1]: https://www.ansible.com/
[2]: http://pre-commit.com/
[3]: https://github.com/willthames/ansible-lint 
