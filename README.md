# Ansible netbackup role

This is an [Ansible](http://www.ansible.com) role to install netbackup linux agent.

References:
- https://www.veritas.com/content/support/en_US/doc/27801100-130821038-0/v118646263-130821038
- https://www.veritas.com/content/support/en_US/doc/27801100-130821038-0/v121344818-130821038

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`.

## Usage

This is an example playbook:

```yaml
---

- hosts: all
  roles:
    - role: amtega.netbackup
      vars:
        netbackup_state: present

        netbackup_server: myserver.acme.com
        netbackup_media_servers:
          - mymediaserver1.acme.com
          - mymediaserver2.acme.com

        netbackup_certificate_fingerprint: >-
          xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx

        netbackup_authorization_token: xxxxxxxxxxxxxxxxxxxx
```

## Testing

Tests are based on [molecule with docker containers](https://molecule.readthedocs.io/en/latest/installation.html).

The tests doesn't install the netbackup packages to avoid registering into servers testing machines.

```shell
cd amtega.netbackup

molecule test
```

## License

Copyright (C) 2020 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- José Enrique Mourón Regueira
