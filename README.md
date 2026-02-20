# [Ansible role firefox](#ansible-role-firefox)

Firefox Installation.

|GitHub|GitLab|Downloads|Version|
|------|------|---------|-------|
|[![github](https://github.com/buluma/ansible-role-firefox/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-firefox/actions)|[![gitlab](https://gitlab.com/shadowwalker/ansible-role-firefox/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-firefox)|[![downloads](https://img.shields.io/ansible/role/d/buluma/firefox)](https://galaxy.ansible.com/buluma/firefox)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-firefox.svg)](https://github.com/buluma/ansible-role-firefox/releases/)|

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
- name: Prepare
  hosts: all
  become: true
  gather_facts: false

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
# https://ftp.mozilla.org/pub/firefox/releases/123.0/SHA512SUMS
firefox_checksum: "sha512:9ab94d078ef9178e2b12ab8aa114eb6f84ea7c9b3055e552156764019a13aeb39fff91f9b402156c5c12b6053df14228bbffffe81199dc6ef967d21fb5a962ba"
firefox_desktop_icon: false
firefox_home: /opt/firefox-{{ firefox_version }}
firefox_image_path: "firefox/browser/chrome/icons/default/default128.png"
firefox_logo: "{{ firefox_home }}/{{ firefox_image_path }}"
firefox_version: "123.0"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-firefox/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.ca_certificates](https://galaxy.ansible.com/buluma/ca_certificates)|[![Build Status GitHub](https://github.com/buluma/ansible-role-ca_certificates/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-ca_certificates/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-ca_certificates/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-ca_certificates)|

## [Context](#context)

This role is part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-firefox/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|all|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|all|
|[Debian](https://hub.docker.com/r/buluma/debian)|all|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|all|

The minimum version of Ansible required is 2.12, tests have been done on:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them on [GitHub](https://github.com/buluma/ansible-role-firefox/issues).

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-firefox/blob/master/LICENSE).

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)

