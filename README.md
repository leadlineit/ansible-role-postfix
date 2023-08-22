# Ansible Galaxy role for install and configure Postfix.

![Build Status](https://github.com/leadlineit/ansible-role-postfix/actions/workflows/ansible-galaxy-ci.yml/badge.svg)
[![Galaxy Role](https://img.shields.io/badge/Ansible--Galaxy-leadlineit.postfix-blue.svg?logo=ansible&logoColor=white)](https://galaxy.ansible.com/leadlineit/postfix/)

This role helps to install and configure Postfix.

Supported OSes
--------------
- Debian 12 (bookworm)
- Debian 11 (bullseye)
- Debian 10 (buster)

Requirements
------------

This role requires Ansible 2.15 or higher.

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows:

```yaml
---
postfix_relayhost: some.host.domain
postfix_relayhost_port: 587
postfix_smtp_tls_cafile: /etc/ssl/certs/ca-certificates.crt
postfix_smtp_sasl_auth_enable: yes
postfix_smtp_sasl_security_options: noanonymous
postfix_smtp_sasl_password_maps: /etc/postfix/sasl/passwd
postfix_smtp_use_tls: yes
postfix_smtp_tls_security_level: encrypt
postfix_smtp_tls_note_starttls_offer: yes
postfix_message_size_limit: 102400000
postfix_maildomain: testdomain.com
postfix_relayhost_user: user-postfix
postfix_relayhost_password: Aver@gEStr0ngPaSSw0rd
postfix_aliases:
  aliases:
    - name: admin
      alias: admin@adminever.com
    - name: google
      alias: google@gmail.com
    - name: yahoo
      alias: yahoo@yahoo.com
```

The variables above are optional. They don't have a default value, so if you don't define them - tasks using them will be skipped. 
You can set only some of them, or not set at all (in this case, you will simply install Bareos-FD with default configuration).

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: servers
  roles:
    - { role: leadlineit.postfix, tags: postfix }
```

License
-------

MIT

Author Information
------------------

This role was created by Artem Kasianchuk.
