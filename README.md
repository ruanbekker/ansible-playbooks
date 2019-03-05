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

## Resources:

NFS Fix:
- https://github.com/rancher/rancher/issues/6452
