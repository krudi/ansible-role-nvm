# ansible-role-nvm

A role for [Ansible](https://github.com/ansible/ansible), that installs [Node Version Manager](https://github.com/nvm-sh/nvm), along with [Node.js](https://github.com/nodejs)

## Requirements

Officially, the requirements from Node [Node Version Manager](https://github.com/nvm-sh/nvm) are packages such as: **curl**, **build-essential** and **libssl-dev**, which are installed automatically with the launch of this role. If the packages are already installed on your machine, this step will be skipped

## Quick start

1. First clone this repository and add into your project directory
2. Include the role in your [Ansible](https://github.com/ansible/ansible) playbook

## Example playbook

Example use of a role that will install the latest LTS version from  [Node.js](https://github.com/nodejs)

```yml
- hosts: all
  roles:
    - role: krudi.nvm
      # This option adds block code that loads the configuration from the Node Version Manager
      ## If you don't have any Node Version Manager loading from files such as **.bashrc**, **.zsh** or **.profile**, this option should be set to **true**
      nvm_nodejs_add_block: false
```

## Additional information

To change the version of Node Version Manager after installing this role, just use the official [Node Version Manager](https://github.com/nvm-sh/nvm) install command

More information can be found here: <https://github.com/nvm-sh/nvm#usage>

## Issue

Have you found a bug in this project or have a suggestion for a new feature? Create a new ticket for the bug or feature, which can be found on the [GitHub](ttps://github.com/krudi/ansible-role-nvm/issues) page
