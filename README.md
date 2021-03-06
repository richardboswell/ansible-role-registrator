# ansible-role-registartor

Ansible playbook to automate installing and maintaining
[Consul Registrator](http://github.com/gliderlabs/registrator).

## Requirements

This role currently requires a working VMware Photon server with enabled Docker
environment.

## Role Variables

```yaml
# Container memory limit -- Use 512MB, type string, or 0 for unlimited
memory_limit: 0MB

# The docker systemd unit file to modify if necessary.
docker_service_unit: /lib/systemd/system/docker.service

# Name server hosts the container should use.
docker_dns_hosts:
  - "{{ inventory_hostname }}"
  
# The Consule service endpoint to use for registering.
consul_service_uri: consul://consul.service.consul:8500
```

## Example playbook

```
---
- hosts: registrator
  sudo: True
  roles:
    - registrator
  vars:
    - ... forthcoming
```

# License and Copyright
 
Copyright 2015 VMware, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

