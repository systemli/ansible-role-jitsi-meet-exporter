# Ansible role to install and configure Jitsi Meet Exporter

[![Build Status](https://travis-ci.com/systemli/ansible-role-jitsi-meet-exporter.svg?branch=master)](https://travis-ci.com/systemli/ansible-role-jitsi-meet-exporter) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-jitsi_meet_exporter-blue.svg)](https://galaxy.ansible.com/systemli/jitsi_meet_exporter/)

This role installs and configure a prometheus metrics exporter for [Jitsi Meet](https://jitsi.org/jitsi-meet/).

Role Variables
--------------

```
prometheus_jitsi_meet_exporter_version: 1.0.1
prometheus_jitsi_meet_exporter_videobridge_url: http://localhost:8888/stats
prometheus_jitsi_meet_exporter_listen: :9888
```

Download
--------

Download latest release with `ansible-galaxy`

	ansible-galaxy install systemli.jitsi_meet_exporter

Example Playbook
----------------

```
- hosts: jitsimeetservers
  roles:
     - { role: systemli.jitsi_meet_exporter }
```

Tests
-----

For developing and testing the role we use Travis CI, Molecule and Vagrant. On the local environment you can easily test the role with

```
pip install molecule-vagrant ansible-lint yamllint
molecule test
```

This requires [Vagrant](https://www.vagrantup.com/downloads.html) to be installed.

License
-------

GPLv3

Author Information
------------------

https://www.systemli.org
