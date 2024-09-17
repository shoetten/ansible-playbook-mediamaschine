# ansible-playbook-mediamaschine

Self-hosted [ente.io](https://ente.io/) encrypted photo storage and audiobook streaming server via [audiobookshelf](https://github.com/advplyr/audiobookshelf).

## Usage

Create a `group_vars/all/vault.yml` file and configure all necessary variables (all prefixed with `vault_`). Then run

```
make deploy
```

This installs Ansible with all requirements and runs the `site.yml` playbook.

You can run a single playbook (e.g. `audiobookshelf.playbook.yml`) via

```
make deploy PLAYBOOK=audiobookshelf.playbook.yml
```
