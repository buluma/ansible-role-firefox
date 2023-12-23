# [Ansible role firefox](#firefox)

Firefox Installation.

|GitHub|Version|Issues|Pull Requests|
|------|-------|------|-------------|
|[![github](https://github.com/buluma/ansible-role-firefox/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-firefox/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-firefox.svg)](https://github.com/buluma/ansible-role-firefox/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-firefox.svg)](https://github.com/buluma/ansible-role-firefox/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-firefox.svg)](https://github.com/buluma/ansible-role-firefox/pulls/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-firefox/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true
  roles:
    - role: buluma.firefox
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-firefox/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: buluma.bootstrap
    - role: buluma.ca_certificates
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-firefox/blob/master/defaults/main.yml):

```yaml
---
# https://github.com/030/ansible-firefox
# https://ftp.mozilla.org/pub/firefox/releases/99.0.1/SHA512SUMS
firefox_checksum: sha512:a122bacbe2cc48301f696696e8854d190e0ce9ce72b39e9df90846214c536730a7190a858295f56e836b263bdc2e4e3041cb3bfad8d7cf483c50478c634c14f5  # yamllint disable-line rule:line-length
firefox_desktop_icon: false
firefox_home: /opt/firefox-{{ firefox_version }}
firefox_image_path: "firefox/browser/chrome/icons/default/default128.png"
firefox_logo: "{{ firefox_home }}/{{ firefox_image_path }}"
firefox_version: "99.0.1"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-firefox/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | Version |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bootstrap.svg)](https://github.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.ca_certificates](https://galaxy.ansible.com/buluma/ca_certificates)|[![Build Status GitHub](https://github.com/buluma/ansible-role-ca_certificates/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-ca_certificates/actions)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-ca_certificates.svg)](https://github.com/shadowwalker/ansible-role-ca_certificates)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-firefox/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/repository/docker/buluma/enterpriselinux/general)|7|
|[Ubuntu](https://hub.docker.com/repository/docker/buluma/ubuntu/general)|all|
|[Debian](https://hub.docker.com/repository/docker/buluma/debian/general)|all|
|[Fedora](https://hub.docker.com/repository/docker/buluma/fedora/general)|all|

The minimum version of Ansible required is 2.1, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-firefox/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-firefox/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-firefox/blob/master/LICENSE).

## [Author Information](#author-information)

[Michael Buluma](https://buluma.github.io/)


### [Special Thanks](#special-thanks)

Template inspired by [Robert de Bock](https://github.com/robertdebock)
