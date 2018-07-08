# Ansible Deploy Docker with Convoy Storage

This will deploy a 3x Manager Node Docker Swarm Cluster with Convoy NFS Storage Plugin

## Bootstrap Python to Nodes:

```bash
$ ansible-playbook -i inventory.ini -u root bootstrap-python.yml
```

## Deploy Docker Swarm Cluster with Convoy Storage Plugin:

```bash
$ ansible-playbook -i inventory.ini -u root docker-swarm.yml
```


