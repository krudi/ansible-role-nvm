# Ansible Role — nvm

Ansible role that installs Node Version Manager (nvm) and a specified Node.js version, with optional shell integration.

## Stack

- Ansible / YAML

## Commands

```bash
ansible-lint       # lint the role
molecule test      # full test (if molecule configured)
```

## Onboarding

**Prerequisites:** Ansible, molecule.

1. `ansible-lint` — verify linting passes
2. `molecule converge` — apply the role
3. `molecule test` — full test including idempotency

---

## Testing

- Run before every PR: `ansible-lint && molecule test`
- Verify nvm and the target Node.js version are accessible after installation

---

## Notes

- nvm installs per-user (not system-wide) — tasks run as the target user
- Shell integration (`.bashrc` / `.zshrc`) is optional, controlled by a variable

---

## Rules

@.ai/rules/ansible.md

---

## For Claude Code

### Rules loaded automatically

| Rule file | Applied to |
|-----------|---|
| `.ai/rules/ansible.md` | `**/*.yml`, `**/*.yaml` |

### Constraints

- nvm installs per-user — tasks must run as the target user (not root)
- Shell integration (`.bashrc` / `.zshrc`) is optional, controlled by a variable in `defaults/main.yml`
- Test idempotency: running the role twice must produce no changes on the second run
