Role Name
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
 - nerdfonts_fonts:          - list of nerdfonts to be installed
   - fontname:               - name of nerdfont
     caskname:               - name of nerdfont in homebrew cask (for MacOS)
     caskname_mono:          - name of mono nerdfont in homebrew cask (for MacOS)

MacOS-Specific:
 - nerdfonts_mono: yes | no  - install mono font from homebrew cask

Dependencies
------------

For MacOS hosts:
 - homebrew

Example Playbook
----------------

    - hosts: deb_clients
      roles:
         - nerdfonts

License
-------

MIT

Author Information
------------------

Andrew Shagayev
