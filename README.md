# Deploy Elasticsearch Cluster

Deploy Elasticsearch 2 Node Cluster with Ansible

## Bootstrap Nodes with Python

```bash
$ ansible-playbook -i inventory.ini -u root tasks/bootstrap-python.yml
```

## Deploy Elasticsearch:

```bash
$ ansible-playbook -i inventory.ini -u root tasks/deploy-elasticsearch-cluster.yml
```
