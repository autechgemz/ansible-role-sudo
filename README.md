# Ansible Role: sudo

## Description

Manage sudo — execute a command as another user

## Requirements

None

## Dependencies

None

## OS Platforms

- Debian family
- RedHat family

## Example Playbook

```
- hosts: all
  roles:
    - sudo
```

## Role Variables

### sudo_package_ensure: (string)

```
sudo_package_ensure: 'present'
```

### sudo_global_config_options: (list)

```
sudo_global_config_options: []
```

### sudo_dropin_config_options: (list)

```
sudo_dropin_config_options: []
```

## Example vars

```
sudo_global_config_options:
  - 'Defaults env_reset'
  - 'Defaults mail_badpass'
  - 'Defaults secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"'
  - 'Defaults use_pty'
  - 'root ALL=(ALL:ALL) ALL'
  - '%admin ALL=(ALL) ALL'
  - '%sudo ALL=(ALL:ALL) ALL'

sudo_dropin_config_options:
  - file: vagrant
    state: present
    content:
      - 'vagrant ALL=(ALL) NOPASSWD: ALL'
  - file: ubuntu
    state: present
    content:
      - 'ubuntu  ALL=(ALL) NOPASSWD: ALL'
```
