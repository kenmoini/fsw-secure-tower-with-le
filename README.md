Secure Ansible Tower with Let's Encrypt
=========

A simple role, to do an important task: secure an Ansible Tower installation with Let's Encrypt.

Assumes default installation of Ansible Tower from latest package, and a FQDN.

Supports RHEL/CentOS 7, Amazon Linux, and Ubuntu 16+

Requirements
------------

Outside of Ansible 2.5 no real requirements needed, most is done with the 'apt', 'letsencrypt', 'lineinfile', 'package', and 'yum' modules.
Make sure to run the role with escalated privilages since we need to install packages and configure services.

Role Variables
--------------

There are two important role variables that needs to be defined

- fqdn - The Fully Qualified Domain Name (FQDN) of the Ansible Tower server, eg, tower.example.com
- le_email - The email address to be passed to Let's Encrypt

Defaults are set to the inventory_hostname and me@example.com

Dependencies
------------

Ansible Tower to be installed already, and privilaged user access

Example Playbook
----------------

Including this role similar to the below example, noting the "become" for privilages and the "fqdn":

    - hosts: tower
      roles:
         - { role: kenmoini.fsw-secure-tower-with-le, become: yes, fqdn: "tower.example.com", le_email: "you@example.com" }

License
-------

GNU GPLv3

Author Information
------------------

Authored by Ken Moini (ken@kenmoini.com) (https://github.com/kenmoini) during tenure at Fierce Software (https://fiercesw.com) (https://github.com/FierceSoftware)
