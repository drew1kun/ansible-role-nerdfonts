Ansible role: nerdfonts
=========

[![MIT licensed][mit-badge]][mit-link]
[![Galaxy Role][role-badge]][galaxy-link]

Cross-platform ansible role for [NerdFonts][nerdfonts] ([on GitHub][nf-git]) installation.

Requirements
------------

One of the following OS (or deriviatives):
 - Debian | Ubuntu
 - MacOS (with [Homebrew][homebrew])

For MacOS:
if Homebrew is not installed on the managed host, install the following role via galaxy:

    ansible-galaxy install drew-kun.homebrew

 And include it in the playbook:

    roles:
        - drew-kun.homebrew

Role Variables
--------------

OS-Agnostic:

    nerdfonts_fonts:                      # list of nerdfonts to be installed
     - fontname:                          # name of nerdfont
       caskname:                          # name of nerdfont in homebrew cask (for MacOS)
       caskname_mono:                     # name of mono nerdfont in homebrew cask (for MacOS)

Debian-Specific:

    nerdfonts_env: system | user/users    # install fonts system- or user-wide
    nerdfonts_deb_fonts_sys_dir:          # system-wide fonts directory
    nerdfonts_deb_fonts_user_dir:         # user-specific fonts directory
    nerdfonts_users:                      # list of users nerdfonts to be installed

MacOS-Specific:

    nerdfonts_mono: yes | no              # install mono font from homebrew cask

Dependencies
------------

None

Example Playbook
----------------

    - hosts: dev_clients_macos
      roles:
        - drew-kun.homebrew
        - drew-kun.nerdfonts

License
-------

[MIT][mit-link]

Author Information
------------------

Andrew Shagayev

[role-badge]: https://img.shields.io/badge/role-drew--kun.nerdfonts-green.svg
[galaxy-link]: https://galaxy.ansible.com/drew-kun/nerdfonts/
[mit-badge]: https://img.shields.io/badge/license-MIT-blue.svg
[mit-link]: https://raw.githubusercontent.com/drew-kun/ansible-nerdfonts/master/LICENSE
[homebrew]: http://brew.sh/
[nerdfonts]: https://nerdfonts.com/
[nf-git]: https://github.com/ryanoasis/nerd-fonts
