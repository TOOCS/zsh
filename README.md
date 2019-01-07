[![Build Status](https://travis-ci.org/TOOCS/zsh.svg?branch=master)](https://travis-ci.org/TOOCS/zsh) [![Ansible Role](https://img.shields.io/ansible/role/36109.svg)](https://galaxy.ansible.com/FlorianKempenich/toocs_zsh)

# TOOCS / Ansible Role: `FlorianKempenich.toocs_zsh`
> #### /!\ This role has been renamed - Old name: `zsh` /!\

Install `zsh` and set it as the default shell.  
Also optionally install `antigen`

> ### TOOCS?
> TOOCS - The Opinionated One-Click Setups are a set of tools / ansible roles designed to setup a system in one click. They are a simple, reliable, way to setup a given tool. You can use them as is, or, inspecting their code, as a tutorial to follow step by step.
>
> They are, as their name suggests, opinionated: while they guarantee to setup the given tool in one click, they do **not** guarantee consistency in _how_ they achieve it, new releases might introduce breaking changes.  
> Read the code and make sure you understand what's happening!

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
      - FlorianKempenich.toocs_zsh
```

Installation w/o antigen:
```
- hosts: sandbox
  tasks:
    - include_role:
        name: FlorianKempenich.toocs_zsh
      vars:
        skip_antigen: true
```

## License
MIT

## Author Information
Find out more about my work: [Florian Kempenich](https://floriankempenich.com)
