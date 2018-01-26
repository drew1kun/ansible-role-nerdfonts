nerdfonts
=========

Cross-platform ansible role for NerdFonts installation.

Requirements
------------

One of the following OS (or deriviatives):
 - Debian | Ubuntu
 - MacOS

Role Variables
--------------

OS-Agnostic:

    - nerdfonts_fonts:              # list of nerdfonts to be installed
       - fontname:                  # name of nerdfont
         caskname:                  # name of nerdfont in homebrew cask (for MacOS)
         caskname_mono:             # name of mono nerdfont in homebrew cask (for MacOS)

Debian-Specific:

    - nerdfonts_env:                # system | user/users
    - nerdfonts_deb_fonts_sys_dir:  # system-wide fonts directory
    - nerdfonts_deb_fonts_user_dir: # user-specific fonts directory
    - nerdfonts_users:              # list of users nerdfonts to be installed

MacOS-Specific:

    - nerdfonts_mono: yes | no      # install mono font from homebrew cask

Dependencies
------------

For MacOS hosts:
 - drewshg312.homebrew

Example Playbook
----------------

    - hosts: deb_clients
      roles:
         - drewshg312.nerdfonts

License
-------

MIT

Author Information
------------------

Andrew Shagayev
