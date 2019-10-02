isset.ufw [![pipeline status](https://gitlab.isset.nl/operations/isset.ufw/badges/master/pipeline.svg)](https://gitlab.isset.nl/operations/isset.ufw/commits/master)
=========

_Installs ufw, maintain application profiles and rules._

Requirements
------------

Ansible 2.5 or above is highly recommended.

Role Variables
--------------

    isset_ufw_package_state: present
    isset_ufw_firewall_state: enabled
    isset_ufw_rules:
      - rule: allow
        port: 8080
        src: example.com
    isset_ufw_applications:
      - name: Grafana
        title: Grafana
        description: Dashboard and graph generator
        ports:
          - 3000/tcp
        sources:
          - 127.0.0.1
          - "{{ lookup('dig', 'example.com') }}"
          
Dependencies
------------

    isset.package

Example Playbook
----------------

    - hosts: all
      become: yes
      roles:
        - role: isset.ufw

License
-------

MIT

Author Information
------------------

Gerben Geijteman <gerben@isset.nl>
