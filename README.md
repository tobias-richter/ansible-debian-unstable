# tobias_richter.debian_unstable

[![Build Status](https://travis-ci.org/tobias-richter/ansible-debian-unstable.svg?branch=master)](https://travis-ci.org/tobias-richter/ansible-debian-unstable)

This role enables unstable repository and is designed to work together
with
[tobias_richter.apt_config](https://galaxy.ansible.com/tobias_richter/apt_config).
The unstable repo is configured with a pin priority of 50.

Steps based on: https://serverfault.com/questions/22414/how-can-i-run-debian-stable-but-install-some-packages-from-testing

## Requirements

This role requires Ansible 2.7 or higher.

## Role Variables

See [defaults/main.yml](defaults/main.yml) for the documented role
variables.

The template for the apt preferences see
[unstable.pref.j2](templates/etc/apt/preferences.d/unstable.pref.j2).

The apt list template is located here: [unstable.list.j2](templates/etc/apt/sources.list.d/unstable.list.j2)

## Example Playbook

This playbook configures apt together with a proxy server / apt-cacher-ng.

    - hosts: debian_unstable
	  roles:
	    - role: tobias_richter.debian_unstable