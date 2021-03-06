ansible-awx-zimbra-multi
========================

This role is compatible with AWX and automates the process of installing multi-server Zimbra Open Source Edition v8.8.15 on CentOS 8

Requirements
------------

1) Must be a fresh CentOS 8 minimal installation
2) Ansible AWX node must have the "netaddr" Python module installed

Role Variables
--------------

    zimbra_timezone: Asia/Singapore
    zimbra_ldap_fqdn: ldap.example.com
    zimbra_mta_fqdn: mta.example.com
    zimbra_proxy_fqdn: proxy.example.com
    zimbra_mailbox_fqdn: mailbox.example.com
    zimbra_admin_password: ansible@zimbra2020

Inventory
---------

Inventory file similar below:

    [zimbra_all:children]
    zimbra_ldap
    zimbra_mta
    zimbra_proxy
    zimbra_mailbox

    [zimbra_ldap]
    192.168.122.111

    [zimbra_mta]
    192.168.122.112

    [zimbra_proxy]
    192.168.122.113

    [zimbra_mailbox]
    192.168.122.114

License
-------

MIT License

Author Information
------------------

Author: Jan Cubillan<br>
GitHub: https://github.com/jancubillan<br>
