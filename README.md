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

## Administration

### Ente

To add a new user to ente, download the ente mobile app. Start the app and touch the logo five times, to activate developer settings.
There you will be able to enter a custom backend url: `https://ente.hoetten.org`. Proceed by registering your account through the app.

Afterwards the admin has to grant the new account more storage and expiry date via the ente-cli. Install the cli on your local computer, e.g. via the [AUR](https://aur.archlinux.org/packages/ente-cli-bin).

```bash
# login into your admin account
ente account add
# update the new account
ente admin update-subscription -u EMAIL --no-limit False
```
