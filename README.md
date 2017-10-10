foreman_proxy_certificates
=========
The role delegates certificate creation to ```foreman_ca_host``` and then deploys those certificates to proxy hosts which this role is being applied to.</br>
Inspired by [openshift-ansible/openshift_node_certificates](https://github.com/openshift/openshift-ansible/tree/master/roles/openshift_node_certificates) role.

Requirements
------------

Role Variables
--------------

| Name    | Description    | Required    | Default    | Values | Examples |
|:--|:--|:-:|:-:|:-:|:--|
| foreman_ca_cert | The path to ca cert | No | /etc/puppetlabs/puppet/ssl/certs/ca.pem | - | - |
| foreman_ca_host | The hostname of the system where the Foreman CA will has been created | Yes | - | - | - |

Dependencies
------------

Example Playbook
----------------

```yaml
---
- name: Create Foreman certificates for proxy hosts
  hosts: proxies
  roles:
  - role: foreman_proxy_certificates
    foreman_ca_host: foreman-master.example.com
```

License
-------
BSD

Author Information
------------------
genadipost@gmail.com
