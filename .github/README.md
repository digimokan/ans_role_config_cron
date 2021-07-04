# ans_role_config_cron

Install and configure the standard UNIX cron daemon.

[![Release](https://img.shields.io/github/release/digimokan/ans_role_config_cron.svg?label=release)](https://github.com/digimokan/ans_role_config_cron/releases/latest "Latest Release Notes")
[![License](https://img.shields.io/badge/license-MIT-blue.svg?label=license)](LICENSE.md "Project License")

## Table Of Contents

* [Purpose](#purpose)
* [Supported Operating Systems](#supported-operating-systems)
* [Quick Start](#quick-start)
    * [Use From Parent Role As Dependency](#use-from-parent-role-as-dependency)
* [Contributing](#contributing)

## Purpose

* Install standard UNIX [cron](https://en.wikipedia.org/wiki/Cron) daemon.
* Configure the cron daemon to start at boot.
* Ensure cron deamon is currently running.
* _NOTE: Use other ansible roles or tasks to schedule cron jobs_.

## Supported Operating Systems

* Arch Linux.

## Quick Start

### Use From Parent Role As Dependency

1. List in parent role's `meta/main.yml`:

   ```yaml
   dependencies:
     - src: https://github.com/digimokan/ans_role_config_cron
   ```

## Contributing

* Feel free to report a bug or propose a feature by opening a new
  [Issue](https://github.com/digimokan/ans_role_config_cron/issues).
* Follow the project's [Contributing](CONTRIBUTING.md) guidelines.
* Respect the project's [Code Of Conduct](CODE_OF_CONDUCT.md).

