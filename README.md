ansible-awx-zimbra-multi
========================

This role is compatible with AWX and automates the process of installing multi-server Zimbra Open Source Edition v8.8.15 on CentOS 8

Requirements
------------

1. Must be a fresh CentOS 8 minimal installation
2. Static network configuration must be already set

Role Variables
--------------

Apply changes to suit your environment.

    zimbra_timezone: Asia/Manila
    zimbra_ldap_fqdn: ldap.example.com
    zimbra_mta_fqdn: mta.example.com
    zimbra_proxy_fqdn: proxy.example.com
    zimbra_mailbox_fqdn: mailbox.example.com
    zimbra_ldap_shortname: ldap
    zimbra_mta_shortname: mta
    zimbra_proxy_shortname: proxy
    zimbra_mailbox_shortname: mailbox
    zimbra_network_name: enp1s0
    zimbra_ldap_ip: 192.168.122.111
    zimbra_mta_ip: 192.168.122.112
    zimbra_proxy_ip: 192.168.122.113
    zimbra_mailbox_ip: 192.168.122.114
    zimbra_reverse_ip: 122.168.192
    zimbra_ldap_ptr: 111
    zimbra_mta_ptr: 112
    zimbra_proxy_ptr: 113
    zimbra_mailbox_ptr: 114
    zimbra_subnet: 192.168.122.0/24
    zimbra_forwarders: 8.8.8.8; 8.8.4.4;
    zimbra_domain: example.com
    zimbra_admin_password: zimbra4ever
    zimbra_system_password: zimbra4ever


Inventory
---------

Inventory file similar below:

    [zimbra_all:children]
    zimbra_ldap
    zimbra_mta
    zimbra_proxy
    zimbra_mailbox

    [zimbra_ldap]
    ldap.example.com ansible_host=192.168.122.111

    [zimbra_mta]
    mta.example.com ansible_host=192.168.122.112

    [zimbra_proxy]
    proxy.example.com ansible_host=192.168.122.113

    [zimbra_mailbox]
    mailbox.example.com ansible_host=192.168.122.114

License
-------

MIT License

Author Information
------------------

Author: Jan Cubillan<br>
GitHub: https://github.com/jancubillan<br>
