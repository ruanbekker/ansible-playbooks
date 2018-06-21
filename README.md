# ansible-playbooks

Repo for Anisble Playbooks

## Examples:

Test:

```
$ ansible -i inventory.ini -u root -m ping all
```

Bootstrap Nodes with Python:

```
$ ansible-playbook -i inventory.ini -u root bootstrap-python.yml
```
