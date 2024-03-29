# Ansible role: nerdfonts

[![MIT licensed][mit-badge]][mit-link]
[![Galaxy Role][role-badge]][galaxy-link]

DEPRECATION NOTICE
----
This role is being deprecated in favor of [ansible-collection-fancyfonts][fancyfonts-github-link].

Collection on Galaxy: [drew1kun.fancyfonts][fancyfonts-galaxy-link]

Description
----

Cross-platform ansible role for [NerdFonts][nerdfonts] ([on GitHub][nf-git]) installation.

Requirements
----

One of the following OS (or deriviatives):

 - Debian | Ubuntu
 - MacOS (with [Homebrew][homebrew])

**NOTE:**

 - Role requires Fact Gathering by ansible!
 - On MacOS only user-specific installation from Homebrew is available

**MacOS:**
if Homebrew is not installed on the managed host, install the following role via galaxy:

```
ansible-galaxy install geerlingguy.homebrew
```

 And include it in the playbook:
```
roles:
- geerlingguy.homebrew
```

Role Variables
----

OS-Agnostic:

| Variable | Description | Default |
|----------|-------------|---------|
| `nerdfonts_fonts[]` | List of nerdfonts to be installed | see [`defaults/main.yml`](defaults/main.yml) |
| `nerdfonts_users[]` | List of users nerdfonts to be installed | see [`vars/debian.yml`](vars/debian.yml) |

Debian-Specific:

| Variable | Description | Default |
|----------|-------------|---------|
| `nerdfonts_deb_env` | Install fonts system- or user-wide | `system` |
| `nerdfonts_deb_fonts_sys_dir` | System-wide fonts directory | `/usr/local/share/fonts` |
| `nerdfonts_deb_fonts_user_dir` | User-specific fonts directory | `~/.local/share/fonts` |

Dependencies
----

None

Example Playbook
----

```yaml
- hosts: dev_clients_macos
  gather_facts: yes
  roles:
  - geerlingguy.homebrew
  - drew1kun.nerdfonts
```

License
----

[MIT][mit-link]

Author Information
----

Andrew Shagayev | [e-mail](mailto:drewshg@gmail.com)

[role-badge]: https://img.shields.io/badge/role-drew1kun.nerdfonts-green.svg
[galaxy-link]: https://galaxy.ansible.com/drew1kun/nerdfonts/
[mit-badge]: https://img.shields.io/badge/license-MIT-blue.svg
[mit-link]: https://raw.githubusercontent.com/drew1kun/ansible-nerdfonts/master/LICENSE
[homebrew]: http://brew.sh/
[nerdfonts]: https://nerdfonts.com/
[nf-git]: https://github.com/ryanoasis/nerd-fonts
[fancyfonts-github-link]: https://github.com/drew1kun/ansible-collection-fancyfonts
[fancyfonts-galaxy-link]: https://galaxy.ansible.com/drew1kun/fancyfonts
