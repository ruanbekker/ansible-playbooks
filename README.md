# ansible-playbooks

Repo for Anisble Playbooks

## Playbooks:

- Docker Swarm
- Convoy Storage
- Metricbeat
- Elasticsearch
- GlusterFS

## Examples:

Test:

```
$ ansible -i inventory.ini -u root -m ping all
```

Bootstrap Nodes with Python:

```
$ ansible-playbook -i inventory.ini -u root bootstrap-python.yml
```

Ping Nodes with a Playbook using a custom directory structure:

```
$ cat myinventory.ini
[rpifleet]
rpi-01 ansible_host=192.168.0.115 ansible_user=pi ansible_ssh_private_key_file=~/.ssh/id_rsa ansible_python_interpreter=/usr/bin/python3
rpi-02 ansible_host=192.168.0.116 ansible_user=pi ansible_ssh_private_key_file=~/.ssh/id_rsa ansible_python_interpreter=/usr/bin/python3
rpi-03 ansible_host=192.168.0.117 ansible_user=pi ansible_ssh_private_key_file=~/.ssh/id_rsa ansible_python_interpreter=/usr/bin/python3
[rpifleet:vars]
ansible_ssh_common_args='-o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null'
```

```
$ cat ansible-playbook -i myinventory.ini playbooks/ping-playbook.yml
```

## Resources:

NFS Fix:
- https://github.com/rancher/rancher/issues/6452
