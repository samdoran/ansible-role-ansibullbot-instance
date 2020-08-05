Ansibullbot Instance
====================
[![Build Status](https://travis-ci.org/samdoran/ansible-role-ansibullbot-instance.svg?branch=master)](https://travis-ci.org/samdoran/ansible-role-ansibullbot-instance)

Create instance for running [Ansibullbot](https://github.com/ansible/ansibullbot).

Requirements
------------

`boto`, `boto3`, and `botocore` installed and configured

Role Variables
--------------

| Name              | Default Value       | Description          |
|-------------------|---------------------|----------------------|
| `botinstance_action` | `create` | Default action to take: `create` or `destroy`. |
| `botinstance_name` | `ansibullbot` | Name tag applied to instance and used for comparing exact count. |
| `botinstance_volume_size` | `100` | Size in GB for the main volume. |
| `botinstance_cloud` | `aws` | Cloud platform where instance will be created. |
| `botinstance_type` | `t2.medium` | Instance type/size to create. |
| `botinstance_region` | `us-east-2` | Region in cloud platform where instance will be created. |
| `botinstance_ssh_keys` | [see `defaults/main.yml`] | Public SSH keys to insert into the instance for logging in. |
| `botinstance_security_group_name` | `Ansibullbot` | Security group name to create in cloud platform. |
| `botinstance_security_group_rules_egress` | [see `defaults/main.yml`] | List of egress ports to allow from the instance. |
| `botinstance_security_group_rules` | [see `defaults/main.yml`] | List of inbound ports allowed to the instance. |
| `botinstance_dns_zone` | `eng.ansible.com` | DNS zone where entries will be created. |
| `botinstance_dns_entries` | [see `defaults/main.yml`] | DNS entries to create. |

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: all
      roles:
         - samdoran.ansibullbot-instance

License
-------

MIT
