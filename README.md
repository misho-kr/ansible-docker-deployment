Ansible role to deploy Docker Engine
====================================

### Goals

Deploy and control Docker Engine with [Ansible playbook](http://docs.ansible.com/ansible/playbooks.html)

Specifically:

* Installation and upgrade of Docker Engine packages
* Start, stop and status query of Docker daemon

### Preparation

1. Install Ansible ([instructions](http://docs.ansible.com/intro_installation.html))
1. Download the playbook from the GitHub repository, as a tar-ball or execute git-clone
1. Define the target hosts

### Supported Environments

* Ubuntu 14-16
* RedHat 7
* CentOS 7
* Fedora 25

### Role Variables

| Name | Default Value | Description |
|-|-|-|
| `docker_engine_type` | `public` | Docker variant -- *EE* (cs) or *CE* (public) |
| `docker_engine_package_version` | `latest` | Docker version |
| `docker_engine_pub_version_major` | `17.03` | Version major number of Docker CE |
| `docker_engine_pub_version_minor` | `0~ce-0` | Version minor number of Docker CE |
| `docker_engine_cs_version_major` | `1.13` | Version major number of Docker EE |
| `docker_engine_cs_version_minor` | `1~cs2-0` | Version minor number of Docker EE |
| `ssl_certificates` | `<empty list>` | SSL certificates in _files/_ dir to deploy on remote hosts |
| `remove_old_docker_engine` | `False` | remove existing Docker Engine package |
| `add_user_to_docker_group` | `True` | add user to _Docker_ group (to run docker commands w/o sudo) |
| `download_cache` | `download.cache` | local directory to save downloaded files |
| `docker_repo_accessible` | `False` | Are Docker package repositories accessible from remote hosts |

### License

[MIS](LICENSE)

### TODO

* Optional download packages to local host (once) to avoid pulling them from every remote host
* Configure Docker daemon to use remote key-value store
* Support SSL cetificates to secure communication wih Docker daemon(s)
* Add tasks to:
  * generate private key and SSL certificate
  * set up Swarm cluster
  * install docker-compose

