# Ansible role to install and configure Jitsi Meet Exporter

[![Integration](https://github.com/systemli/ansible-role-jitsi-meet-exporter/actions/workflows/main.yml/badge.svg?branch=main)](https://github.com/systemli/ansible-role-jitsi-meet-exporter/actions/workflows/main.yml)
[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-jitsi_meet_exporter-blue.svg)](https://galaxy.ansible.com/systemli/jitsi_meet_exporter/)

This role installs and configures a prometheus metrics exporter for [Jitsi Meet](https://jitsi.org/jitsi-meet/).

## Role Variables

```yaml
prometheus_jitsi_meet_exporter_version: 1.4.1
prometheus_jitsi_meet_exporter_videobridge_url: http://localhost:8080/colibri/stats
prometheus_jitsi_meet_exporter_listen: :9888
```

## Download

Download latest release with `ansible-galaxy`

```shell
ansible-galaxy install systemli.jitsi_meet_exporter
```

## Example Playbook

```yaml
- hosts: jitsimeetservers
  roles:
     - { role: systemli.jitsi_meet_exporter }
```

## Testing & Development

### Tests

For developing and testing the role we use GitHub Actions and Molecule with the Docker driver. CI runs the role on Debian 13 and 12 and Ubuntu 22.04 and 20.04 (see `.github/workflows/main.yml`).

To test the role locally, install Docker (or a compatible runtime), `molecule` and `molecule-plugins[docker]`, then run:

```shell
molecule test
```

Use `molecule converge` to apply the role to a container and `molecule login` to inspect it. The local scenario in `molecule/default/` uses Debian 13.

## License

GPLv3

## Author Information

<https://www.systemli.org>
