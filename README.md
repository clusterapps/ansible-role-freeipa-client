# ansible-freeipa-client

## Synopsis

```yaml
- hosts: all
  vars:
    freeipaclient_servers: 
      - ipa.demo1.freeipa.org
      - ipa.demo2.freeipa.org
    freeipaclient_domain: ipa.demo1.freeipa.org
    freeipaclient_enroll_user: admin
    freeipaclient_enroll_pass: Secret123
  roles:
     - alvaroaleman.freeipa-client
```

## Description

This role allows to join clients to an ipa domain.

## Requirements

* CentOS 7
* Fedora 24+
* Ubuntu Trusty
* Ubuntu Xenial

## Role Variables

* ``freeipaclient_servers``: List of IP/Hostname of IPA servers to use (string, mandatory)
* ``freeipaclient_domain``: Domain to use (string, mandatory)
* ``freeipaclient_enroll_user``: Username to enroll host in domain (string, mandatory)
* ``freeipaclient_enroll_pass``: Password to enroll host in domain (string, mandatory)
* ``freeipaclient_hostname``: The hostname to use for the client (string, default: output of ``uname -n``)
* ``freeipaclient_dns_server``: DNS server to configure. This will not do anything if variable is empty (string)
* ``freeipaclient_force_join``: Whether to overwrite an already existing host entry of requested name (boolean, default: ``false``)
* ``freeipaclient_enable_ntp``: Whether to enable ntp. Kerberos won't work if the time of master and client drift too much (boolean, default: ``true``)
* ``freeipaclient_all_ip_addresses``: Whether to add all routable ip addresses to DNS (boolean, default: ``true if not Trusty, else false``)


## License

GNU AFFERO GENERAL PUBLIC LICENSE Version 3


## Author Information

This project has been forked from [Alvaro Aleman](https://github.com/alvaroaleman/ansible-freeipa-client).
