Ansible role to deploy Docker Engine
====================================

### Goals

Automate all Docker Engine deployment and control actions with [Ansible playbook](http://docs.ansible.com/ansible/playbooks.html):

* Installation and upgrade
* Start, stop amd status query

### Preparation

1. Install Ansible ([instructions](http://docs.ansible.com/intro_installation.html))
1. Download the playbook from the GitHub repository, as a tar-ball or execute git-clone
1. Define the target hosts

The playbook will run on remote hosts listed in the [inventory](http://docs.ansible.com/intro_inventory.html). Use the [hosts.empty] as template, copy to _hosts_ and add your servers.

### Execution

```bash
$ ansible-playbook -v deploy.yml -k -K -f 10
SSH password:
SUDO password[defaults to SSH password]:

...
```

Notes:

* Enable [passwordless login](http://linuxconfig.org/passwordless-ssh) to target hosts to avoid the prompt for password and dtop the "-k" switch
* If __sudo__ on the target hosts does not require password, then "-K" switch is not needed
* Ansible runs playbook actions in parallel (5 hosts) by default, use "-f" switch to scale up or down

