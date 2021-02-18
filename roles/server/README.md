# Ansible Role - mafalb.squid.server

Installs squid. Tested with

- CentOS 7
- CentOS 8
- CentOS Stream 8
- Fedora 32
- Fedora 33
- Ubuntu 18.04 (bionic)
- Ubuntu 20.04 (focal)
- Debian 9 (stretch)
- Debian 10 (buster)

## Basic Usage

You can provide your own template for squid.conf

```yaml
- name: install squid
  hosts: localhost
  roles:
  - role: mafalb.squid.server
    squid_cfg_template: path_to_squid.conf.j2
```

With the default template the whole squid configuration can be written as yaml in the squid_cfg dictionary. squid_cfg will be merged with [squid_default_cfg](vars/main.yml).

What follows is just a minimum example to demonstrate the concept. Have a look at [squid_default_cfg](vars/main.yml) and of course the squid documentation for the [recommended minimum acl](http://www.squid-cache.org/Doc/config/acl/). In other words: do not use this in production.

```yaml
- name: install squid
  hosts: localhost
  roles:
  - role: mafalb.squid.server
    squid_cfg:
      acl:
        myhosts:
        - src 127.0.0.1
        - src 192.168.0.10
      http_access:
      - allow myhosts
      - deny all
```

## Variables

---

### squid_state

specify absent to get rid of squid

```yaml
squid_state: present  # present|absent
```

---

### squid_cfg_template

Specify your own template for squid.conf instead of the default

```yaml
squid_cfg_template: squid.conf.j2   
```

---

### squid_cfg

The default template for squid.conf uses squid_cfg to hold the configuration

```yaml
squid_cfg: { ... }
```

---

## License

Copyright (c) 2020,2021 Markus Falb <markus.falb@mafalb.at>

GPL-3.0-or-later
