[![Build Status](https://travis-ci.org/FlorianKempenich/ansible-role-zsh.svg?branch=master)](https://travis-ci.org/FlorianKempenich/ansible-role-zsh) [![Ansible Role](https://img.shields.io/ansible/role/23206.svg)](https://galaxy.ansible.com/FlorianKempenich/zsh)

# Ansible role: `zsh`
Install `zsh` and set it as the default shell.  
Also optionally install `antigen`

## Requirements
This role is only working on Ubuntu/Debian & OSX.

If installing `antigen`, do not forget to add the `antigen` configuration to your `.bashrc`/`.zshrc`.  
**Example `antigen` configuration in `.zshrc` :**
```
source ~/.antigen/antigen.zsh

antigen use oh-my-zsh

antigen bundle virtualenvwrapper
antigen bundle zsh-users/zsh-syntax-highlighting
antigen bundle zsh-users/zsh-autosuggestions

antigen theme agnoster

antigen apply
```

## Role Variables
By default this role will install `antigen`.
To prevent that set the variable: `skip_antigen` to `true`

## Example Playbook
Basic installation w/ antigen:
```
- hosts: sandbox
  roles:
      - FlorianKempenich.zsh
```

Installation w/o antigen:
```
- hosts: sandbox
  tasks:
    - include_role:
        name: FlorianKempenich.zsh
      vars:
        skip_antigen: true
```

## License
MIT

## Author Information
Find out more about my work: [Florian Kempenich](https://floriankempenich.com)
