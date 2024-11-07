ZSH installer
=========

Installer for zsh, oh my zsh and powerlevel10 theme

Description
-----------

Zsh is a powerfull shell with a lot of capacities. It will make you forget bash !

[Oh-my-zsh](https://ohmyz.sh/) is a framework that makes zsh easier to use.

And [Powerlevel10](https://github.com/romkatv/powerlevel10k) is a popular customizable theme for oh-my-zsh.

![Powerlevel prompt example](https://sacoche.libre34.org/s/aofHRSib9kfYg8d/preview)

After installation, you can customize your prompt with powerlevel10 wizard:

`p10k configure`

Or edit file ~/.p10k.zsh

See: <https://github.com/romkatv/powerlevel10k?tab=readme-ov-file#configuration-wizard>

To customize color, you can change POWERLEVEL9K_DIR_BACKGROUND value on line 226.

See colors with :

`for code in {000..255}; do print -P "%F{$code}$code: %F{$code}Color: \uf445\uf445"; done`

Requirements
------------

sudo access required, set ansible_become_password for each node.

Powerlevel10 requires specific fonts, see:

<https://github.com/romkatv/powerlevel10k?tab=readme-ov-file#manual-font-installation>

On host for remote access or on node for local use you may have to change your terminal settings.

In profile settings, check custom font and choose "MesloLGS NF".

Your terminal encoding must be set on unicode - UTF8.

Role Variables
--------------

welcome_word: none

Change it if you want to display a short message with toilet when opening terminal.

zsh_root: true

By default, zsh is installed for root account, set to false to keep bash on root.

An animal random cowsay advertising is set by default, just remove it from ~/.zshrc if you want or set :

cow_message: none

zsh-plugins installed by default:

    plugins:
      - git
      - compleat
      - history
      - history-substring-search
      - rsync
      - sudo
      - zsh-autosuggestions
      - colored-man-pages
      - pyenv
      - z
      - zsh-syntax-highlighting
      - web-search
      - dirhistory

For nodes with graphical desktop, change that var to true:

install_font: false

Dependencies
------------

Does not depend on any other role.

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

