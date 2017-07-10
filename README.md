drhelius.docker
=========

[![Ansible Galaxy](https://img.shields.io/badge/galaxy-drhelius.docker-blue.svg)](https://galaxy.ansible.com/drhelius/docker/) [![Build Status](https://travis-ci.org/drhelius/docker-ansible-role.svg?branch=master)](https://travis-ci.org/drhelius/docker-ansible-role)

Ansible role to install and configure Docker CE and Docker Compose on CentOS, Debian, Ubuntu, Fedora and RedHat.

Role Variables
--------------

```yaml
# Docker channel, stable or edge
docker_channel: stable

# Enable installation of Docker Compose, yes or no
docker_compose: no
# Docker Compose version to install. It will be updated if an older version is found.
docker_compose_version: 1.14.0
# Where to install Docker Compose
docker_compose_path: /usr/local/bin/docker-compose

# Docker storage driver: aufs, btrfs, devicemapper, overlay or overlay2
docker_storage_driver:
# Device name for the storage driver:
docker_block_device:
# Mount options when mounting Btrfs
docker_mount_opts:

# Setup Docker service to use HTTP_PROXY
docker_http_proxy:
# Setup Docker service to use HTTPS_PROXY
docker_https_proxy:
# NO_PROXY hosts
docker_no_proxy_params:

# Docker daemon configuration can be setup with a JSON file, as described here: https://docs.docker.com/engine/reference/commandline/dockerd/#linux-configuration-file
docker_config: {}

# It can also be provided with individual variables. JSON file will be automatically populated with set variables:
docker_api_cors_header:
docker_authorization_plugins:
docker_bip:
docker_bridge:
docker_cgroup_parent:
docker_cluster_store:
docker_cluster_store_opts:
docker_cluster_advertise:
docker_debug:
docker_default_gateway:
docker_default_gateway_v6:
docker_default_runtime:
docker_default_ulimits:
docker_disable_legacy_registry:
docker_dns:
docker_dns_opts:
docker_dns_search:
docker_exec_opts:
docker_exec_root:
docker_fixed_cidr:
docker_fixed_cidr_v6:
docker_graph:
docker_group:
docker_hosts:
docker_icc:
docker_insecure_registries:
docker_ip:
docker_iptables:
docker_ipv6:
docker_ip_forward:
docker_ip_masq:
docker_labels:
docker_live_restore:
docker_log_driver:
docker_log_level:
docker_log_opts:
docker_max_concurrent_downloads:
docker_max_concurrent_uploads:
docker_mtu:
docker_oom_score_adjust:
docker_pidfile:
docker_raw_logs:
docker_registry_mirrors:
docker_runtimes:
docker_selinux_enabled:
docker_swarm_default_advertise_addr:
docker_storage_driver:
docker_storage_opts:
docker_tls:
docker_tlscacert:
docker_tlscert:
docker_tlskey:
docker_tlsverify:
docker_userland_proxy:
docker_userns_remap:
```


Example Playbook
----------------

```yaml
- hosts: all
  roles:
     - drhelius.docker
```
```yaml
- hosts: all
  vars:
    - docker_compose: yes
    - docker_channel: edge
  roles:
     - drhelius.docker
```
```yaml
- hosts: all
  vars:
    - docker_compose: yes
    - docker_storage_driver: devicemapper
    - docker_block_device: /dev/sda3
  roles:
     - drhelius.docker
```
License
-------

MIT
