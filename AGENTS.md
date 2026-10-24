# AGENTS.md

Ansible role that installs and configures the Prometheus Jitsi Meet exporter (systemd service).

## Layout

- `defaults/main.yml`: role variables (exporter version, videobridge URL, listen address)
- `tasks/main.yml`: download and install the exporter, deploy the service
- `templates/`, `handlers/`, `vars/`, `meta/`: service template, handlers, internal vars, role metadata
- `molecule/default/`: integration test (Docker, Debian 13)

## Checks

- `ansible-lint` must pass with the default configuration (no repo-specific config); it creates `.ansible/`, never commit it
- `molecule test` runs the role in a container; CI runs it via `.github/workflows/main.yml`

## Conventions

- Use fully qualified module names (`ansible.builtin.*`)
- Give every task a `name`
- New or changed role variables need an entry in `defaults/main.yml` and the README
- Exporter version bumps are normally done by dedicated "Bump prometheus-jitsi-meet-exporter" PRs

## Commits and PRs

- Write in English, use conventional commit titles (`feat:`, `fix:`, `chore:`, `ci:`; `!` for breaking changes)
- The PR title sets the release-drafter label (`enhancement`, `bug`, `chore`, `breaking`); a breaking change bumps the major version
- Open PRs as draft and fill in `.github/pull_request_template.md`: what changed and why, plus a breaking changes section if needed
- Do not list changed files or claim test results in the description; CI covers that
