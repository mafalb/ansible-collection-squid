# Ansible Role - mafalb.squid.server

Run a very basic squid server with default config. I use it for CI.

## Basic Usage

```yaml
- name: install squid
  hosts: localhost
  roles:
  - role: mafalb.squid.server
```

This role comes with a default configuration which might be good enough for some simple use cases, but probably you want to supply your own configuration.

1. Write your own template


```yaml
- name: install squid
  hosts: localhost
  roles:
  - role: mafalb.squid.server
    squid_template: path_to_your_squid_conf_template
```

2. Use the abstraction built into the default template

3. Extend the default template

## Variables

## License

GPLv3
