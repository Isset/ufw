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
    isset_ufw_default_protocol: any
    isset_ufw_rules:
      - rule: allow
        name: CAdvisor
        src: office.isset.net
        port: 8080
    isset_ufw_applications:
      - name: CAdvisor
        title: Google Cgroups Advisor
        description: Tracks Cgroups containers and system resources
        ports:
          - 8080/tcp
          
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
