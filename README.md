Ansible role for dmg-install
==================================

Installs a dmg file on a MacOS system

[![CircleCI](https://img.shields.io/circleci/build/github/mongodb-ansible-roles/ansible-role-dmg-install/master?style=flat-square)](https://circleci.com/gh/mongodb-ansible-roles/ansible-role-dmg-install)

Requirements
------------

None

Role Variables
--------------

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-------:|:--------:|
| `dmg_download_dest` | Location to download dmg | string | "" | true |
| `dmg_download_url` | URL of dmg | string | "" | true |
| `dmg_stat` | Path to stat if dmg is already installed | string | "" | true |
| `dmg_mount_path` | Where to mount dmg | string | "" | true |

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: ansible-role-dmg-install
      vars:
        dmg_download_dest: /var/root/osx-command-line-tools.dmg
        dmg_download_url: https://s3.whatever.com/command_line_tools.dmg
        dmg_stat: /Library/Developer/CommandLineTools/
        dmg_mount_path: /Volumes/command-line-tools
```

Development
-----------

Testing this role locally requires the CircleCI [Local CLI](https://circleci.com/docs/2.0/local-cli/).

To install the CLI for macOS and Linux, invoke the following command:

    $ curl -fLSs https://circle.ci/cli | DESTDIR=/usr/local/bin bash

After installing the CLI, invoke the following command to run the Molecule tests:

    $ make test

License
-------

[Apache License](LICENSE)
