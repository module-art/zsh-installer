Role Name
=========

Installer for zsh, oh my zsh and powerlevel10 theme

Requirements
------------

Powerlevel10 require specific fonts, see:

<https://github.com/romkatv/powerlevel10k?tab=readme-ov-file#manual-font-installation>

Your terminal encoding must be set on unicode - UTF8.

Role Variables
--------------

welcome_word: none

Change it if you want to display a short message with toilet when opening terminal.

zsh_root: true

By default, zsh is installed for root account, set to false to keep bash on root.

Some tasks need to set ansible_become_password in host_vars for each host.

Dependencies
------------

Example Playbook
----------------

For local install

    - name: zsh ansible
      hosts: localhost
      connection: local
 
      roles:
        - zsh-installer

License
-------

BSD

Author Information
------------------

After installation, you can customize your prompt with powerlevel10 wizard:

`p10k configure`

Or edit file ~/.p10k.zsh

See: <https://github.com/romkatv/powerlevel10k?tab=readme-ov-file#configuration-wizard>

A cowsay advertising is set by default, just remove it from ~/.zshrc if you want.

See in default/main.yml the plugin list that will be installed.
