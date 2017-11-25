# Ansible Role: Beanstool

[![Build Status](https://travis-ci.org/applestump/ansible-role-beanstool.svg?branch=master)](https://travis-ci.org/applestump/ansible-role-beanstool)

An Ansible Role that installs [`beanstool`](https://github.com/src-d/beanstool), a cli tool for monitoring a Beanstalk queue on RedHat/CentOS (v7) or Debian/Ubuntu (14.04 / "Jessie").

## Requirements

Requires Beanstalk. See [`vpeltot.beanstalkd`](https://galaxy.ansible.com/vpeltot/beanstalkd/) for a suitable beanstalkd installation role.

## Role Variables
Available variables are listed below, along with default values (see `defaults/main.yml`):

    beanstool_version: 0.2.0

The version of beanstool to install.

    beanstool_file_name: "beanstool_v{{ beanstool_version }}_linux_amd64"

The file name of the associated beanstool file.

    beanstool_file_path: "{{ beanstool_file_name}}.tar.gz"

The filename and extension of the beanstool file.

    beanstool_src_url: "https://github.com/src-d/beanstool/releases/download/v{{ beanstool_version }}/{{ beanstool_file_path }}"

The URI to use for the beanstool download.

## Dependencies

  - beanstalkd (no specific role requirement)

## Example Playbook

    - hosts: all
      roles:
        - vpeltot.beanstalkd   #Any beanstalk role can be used, this is only a suggestion
        - applestump.beanstool

## License

MIT / BSD

## Author Information

This role was created in 2017 by Matt Lody, and uses some of Jeff Geerling's docker test components (thanks Jeff!).
