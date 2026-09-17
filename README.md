# ansible-role-nvm

A role for [Ansible](https://github.com/ansible/ansible), that installs [Node Version Manager](https://github.com/nvm-sh/nvm), along with [Node.js](https://github.com/nodejs).

## Requirements

This role does not need any additional required packages.

## Quick start

1. First clone this repository and add into your project directory.
2. Include the role in your [Ansible](https://github.com/ansible/ansible) playbook.

## Example playbook

Example use of a role, that will install the latest LTS version of [Node.js](https://github.com/nodejs).

```yml
- hosts: all
  roles:
    - role: krudi.nvm
      nodejs:
        install: true
        version: 22
      nvm:
        install: true
        # This option adds a block of code to ~/.bashrc that loads the Node Version Manager.
        # If you don't already have Node Version Manager loading from a file such as **.bashrc**, **.zshrc** or **.profile**, this option should be set to **true**.
        add_block: true
```

## Role variables

| Variable         | Default                                                           | Description                                                  |
| ---------------- | ------------------------------------------------------------------ | -------------------------------------------------------------- |
| `nodejs.install` | `true`                                                             | Whether Node.js should be installed.                            |
| `nodejs.version` | `22`                                                               | The Node.js major version to install from NodeSource.           |
| `nvm.install`    | `true`                                                             | Whether Node Version Manager should be installed.               |
| `nvm.script`     | `https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh`  | The install script URL used to install nvm.                     |
| `nvm.add_block`  | `false`                                                            | Whether to add the nvm initialization block to `~/.bashrc`.     |

See `defaults/main.yml` for the current defaults.

## Additional information

To change the version of Node Version Manager after installing this role, just use the official [Node Version Manager](https://github.com/nvm-sh/nvm) install command.

More information can be found here: <https://github.com/nvm-sh/nvm#usage>.

## Testing

This role includes a [Molecule](https://ansible.readthedocs.io/projects/molecule/) test scenario under `molecule/default`. Run it with `molecule test` (requires Docker and provisions real containers, so run it deliberately rather than as part of routine checks).

## Issue

Have you found a bug in this project or have a suggestion for a new feature? Create a new ticket for the bug or feature, which can be found on the [GitHub](https://github.com/krudi/ansible-role-nvm/issues) page.
