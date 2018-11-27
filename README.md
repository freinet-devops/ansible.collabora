[![Build Status](https://travis-ci.org/uniQconsulting-ag/ansible.collabora.svg?branch=master)](https://travis-ci.org/uniQconsulting-ag/ansible.collabora)

[![Alt text](https://www.uniqconsulting.ch/images/logo.png)](https://www.uniqconsulting.ch/)

Collabora CODE with Ansible
=================

This is installing collabora CODE on CentOS7 server.    
Nginx is doing reverse proxy and ssl offloading with self signed cert by default.

Requirements
------------

* Currently only tested with CentOS 7
* Ansible 2.4 or higher is required for this Ansible Role

Role Variables
--------------
The following variables can be overridden:

# uniQconsulting.collabora role defaults/main.yml
* collabora_admin_user: admin    
* collabora_admin_password: 'changeme1'    

# install ngingx reverse proxy on top of collabora
* collabora_nginx_ssl_cert_days: 3650    
* collabora_nginx_ssl_cert_host: "{{ansible_fqdn}}"    
* collabora_nginx_ssl_cert_port: 8443    
* collabora_nginx_ssl_cert_dir: /etc/nginx    
* collabora_nginx_ssl_cert_key: "{{collabora_nginx_ssl_cert_dir}}/collabora_key.pem"    
* collabora_nginx_ssl_cert_crt: "{{collabora_nginx_ssl_cert_dir}}/collabora_crt.pem"    
* collabora_nginx_ssl_cert_chain: "{{collabora_nginx_ssl_cert_dir}}/collabora_ca_chain.pem"    

Dependencies
------------

This Ansilbe Role has no dependencies to other Ansilbe Roles

Example Playbook
----------------

Example playbooks for this role are located in ´test´ folder:

uniQconsulting ag
-----------------

uniQconsulting ag is a company in Switzerland with Offices in Bassersdorf, Basel and St. Gallen

License
--------------
https://opensource.org/licenses/LGPL-3.0    
Copyright (c) uniQconsulting ag - Chris Ruettimann <cruettimann@uniqconsulting.ch>
