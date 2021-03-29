# promtail-for-linux

Deploys promtail for linux

## Variables

Uses `group_vars` for group level variables such as `promtail_version` and `host_vars` for variables such as `service_name`

## Secrets

This role uses ansible-vault to decrypt the secret value such as `loki_password` and from the root directory where the `inventory.ini` resides, you need to create the secret with:

```
$ ansible-secret create group_vars/promtail_group/vault
```

and set the encryption password, then provide the config:

```yaml
vault_loki_password: "loki-password-goes-here"
```

And from the `group_vars/promtail_group/vars` you can see its accessible via:

```
loki_password: "{{ vault_loki_password }}"
```

To deploy this playbook without asking for the vault password, then save the vault password to `./vault.pass` and:

```
$ ansible-playbook \
  --inventory inventory.ini \
  --vault-password-file ./vault.pass \
  playbooks/promtail-for-linux.yml
```

To ask for the password:

```
$ ansible-playbook \
  --inventory inventory.ini \
  --ask-vault-pass \
  playbooks/promtail-for-linux.yml
```
