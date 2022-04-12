# Ansible Role: Postfix

Installs Postfix server on Debian and Ubuntu servers.

## Dependencies

  none

## Installation

### Ansible 2+

Using ansible galaxy cli:

```shell
ansible-galaxy install alphanodes.postfix
```

## Role Variables

Available variables can be found in `defaults/main.yml`

## Example Playbook

```yaml
    - hosts: myserver
      vars:
        postfix_root_alias: 'my@mail.com'
      roles:
        - alphanodes.postfix
```

## Example Playbook with google relay

```yaml
    - hosts: myserver
      vars:
        postfix_root_alias: 'my@mail.com'
        postfix_relayhost: smtp.gmail.com
        postfix_relayhost_port: 587
        postfix_sasl_auth_enable: true
        postfix_sasl_password_maps:
          - 'smtp.gmail.com me@gmail.com:my_top_secret_password'
      roles:
        - alphanodes.postfix
```

## License

GPL Version 3

## Author Information

This role was created in 2022 by [AlphaNodes](https://alphanodes.com/).
