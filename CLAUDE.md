# Ansible Role — nvm

Ansible role that installs Node Version Manager (nvm) and a specified Node.js version per-user.

@AGENTS.md

## For Claude Code

### Rules loaded automatically

| Rule file | Applied to |
|-----------|---|
| `.ai/rules/ansible.md` | `**/*.yml`, `**/*.yaml` |

### Constraints

- nvm installs per-user — tasks must run as the target user (not root)
- Shell integration (`.bashrc` / `.zshrc`) is optional, controlled by a variable in `defaults/main.yml`
- Test idempotency: running the role twice must produce no changes on the second run
