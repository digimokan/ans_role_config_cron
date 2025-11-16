# ans_role_config_cron

Install and configure the standard UNIX cron daemon.

[![Release](https://img.shields.io/github/release/digimokan/ans_role_config_cron.svg?label=release)](https://github.com/digimokan/ans_role_config_cron/releases/latest "Latest Release Notes")
[![License](https://img.shields.io/badge/license-MIT-blue.svg?label=license)](LICENSE.md "Project License")

## Table Of Contents

* [Purpose](#purpose)
* [Supported Operating Systems](#supported-operating-systems)
* [Quick Start](#quick-start)
    * [Use From Playbook](#use-from-playbook)
* [Role Options](#role-options)
* [Contributing](#contributing)

## Purpose

* Install the standard UNIX [cron](https://en.wikipedia.org/wiki/Cron) daemon.
* Configure the cron daemon to start at boot.
* Ensure the cron deamon is currently running.
* Configure a set of cron jobs to run as specified user(s), or as root.

## Supported Operating Systems

* Ubuntu.
* Arch Linux.
* FreeBSD.

## Quick Start

### Use From Playbook

1. Create `requirements.yml` in ansible project root, and add this content:

```yaml
# requirements.yml
- src: https://github.com/digimokan/ans_role_config_cron
```

2. From the project root directory, install/download the role:

```shell
$ ansible-galaxy install --role-file requirements.yml --roles-path ./roles --force-with-deps
```

* _NOTE:_ `--force-with-deps` _ensures subsequent calls download updates_

3. Include the role like any local role, from the project playbook:

   ```yaml
   # playbook.yml
   - hosts: localhost
     connection: local
     tasks:
       - name: "Configure cron jobs for all users"
         ansible.builtin.include_role:
           name: ans_role_config_cron
         vars:
           cfg_cron_jobs:
             - job_label: "ansible_run_main_bkup"
               job_user: "root"
               job_minute: "0"   # may omit
               job_hour: "2"     # may omit
               job_day: "*"      # may omit
               job_month: "*"    # may omit
               job_weekday: "*"  # may omit
               job_cmd: "/usr/local/bin/bkup_script.sh"
   ```

## Role Options

Vars with default values, which can be overridden in the playbook:

  * [overridable](../defaults/main/overridable/)

## Contributing

* Feel free to report a bug or propose a feature by opening a new
  [Issue](https://github.com/digimokan/ans_role_config_cron/issues).
* Follow the project's [Contributing](CONTRIBUTING.md) guidelines.
* Respect the project's [Code Of Conduct](CODE_OF_CONDUCT.md).

