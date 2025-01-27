# Ubuntu Autoinstall

[![Badge: Ubuntu](https://img.shields.io/badge/Ubuntu-E95420.svg?logo=ubuntu&logoColor=white)](#readme)
[![Badge: GitHub](https://img.shields.io/badge/GitHub-181717.svg?logo=github&logoColor=white)](#readme)
[![Badge: License](https://img.shields.io/github/license/cyclenerd/ubuntu-autoinstall)](https://github.com/Cyclenerd/ubuntu-autoinstall/blob/master/LICENSE)

This repository provides GitHub Actions workflows to create personalized Ubuntu installation images (ISO) with your preferred configurations and packages pre-installed.

> [!CAUTION]
> **WARNING: Data Loss Risk!**
>
> This installation image will:
> * Automatically partition and format storage devices
> * Delete ALL existing data without prompting
> * Proceed without user intervention
>
> Backup your data before proceeding!

## Quick Start

1. Clone this repository.
1. Customize `autoinstall.yaml`.
1. Let GitHub Actions build your ISO.
1. Download artifact `ubuntu-autoinstall.iso.zip`
1. Flash ISO to USB flash drive using with [balenaEtcher](https://etcher.balena.io/) or `dd`.

## Features

Automation:

* GitHub Actions automated build process
* Unattended installation
* Pre-configured system settings

User Setup:

* Pre-configured user `ubuntu` with sudo privileges
* Password authentication
* Essential group memberships

System Configuration

* DHCP network configuration
* Automated driver installation
* SSH server with password authentication
* Direct storage layout
* Pre-installed packages and current system updates

## Password

Create new password hash:

```bash
openssl passwd -6 '[YOUR-PASSWORD]'
```

Update `autoinstall.yaml` YAML:

```yaml
autoinstall:
  user-data:
     users:
       - name: ubuntu
         passwd: '[HASH]'
```

## Documentation

For detailed configuration options, see [Autoinstall configuration reference manual](https://canonical-subiquity.readthedocs-hosted.com/en/latest/reference/autoinstall-reference.html).

## License

All files in this repository are under the [Apache License, Version 2.0](LICENSE) unless noted otherwise.
