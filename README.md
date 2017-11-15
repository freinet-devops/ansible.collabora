# Collabora Ansible Role    
This is installing collabora CODE on CentOS7 server.    
SSL is disabled on collabora loolwsd.    
Nginx is doing reverse proxy and ssl offloading with self signed cert by default.    

## Execution Requirements
- Tested on CentOS 7

## Role Variables

The following variables can be overridden:
# joe-speedboat.collabora role defaults/main.yml
collabora_admin_user: admin    
collabora_admin_password: 'changeme1'    

# install ngingx reverse proxy on top of collabora
collabora_nginx_ssl_cert_days: 3650
collabora_nginx_ssl_cert_host: "{{ansible_fqdn}}"
collabora_nginx_ssl_cert_port: 8443
collabora_nginx_ssl_cert_dir: /etc/nginx
collabora_nginx_ssl_cert_key: "{{collabora_nginx_ssl_cert_dir}}/collabora_key.pem"
collabora_nginx_ssl_cert_crt: "{{collabora_nginx_ssl_cert_dir}}/collabora_crt.pem"
collabora_nginx_ssl_cert_chain: "{{collabora_nginx_ssl_cert_dir}}/collabora_ca_chain.pem"


## Features
Creates a self signed cert if not present

## example playbooks for this role are located in `test` folder:
 * `playbook.yml`: Role for testing


# License
https://opensource.org/licenses/LGPL-3.0    
Copyright (c) Chris Ruettimann <chris@bitbull.ch>  

