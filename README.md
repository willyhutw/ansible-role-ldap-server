# Ansible LDAP Server

This is a Ansible role to install OpenLDAP Server (support Ubuntu16.04 / Centos7)

## Requirements

Ansible 2.1

## Role Variables

|Variable|Default Value|Description|
|---|---|---|
```dc_main```|example|main domain component name.
```dc_string```|dc=example,dc=com|domain components string.
```ldap_admin_id```|ldapadm|ldap manager.
```ldap_admin_password```|password|password of ldap manager.
```ldap_user_id```|ldapuser|ldap default user.
```ldap_user_password```|password|password of default ldap user.

## Example
```
### create a requirements.yml
- src: git+https://github.com/willyhutw/ansible-role-ldap-server.git
  name: ldap-server

### create a playbook.yml
- hosts: all
  become: yes
  roles:
    - roles/ldap-server

### install this role
ansible-galaxy install -r requirements.yml -p ./roles

### run it!
ansible-playbook -i '192.168.33.141,' playbook.yml \
-e "ansible_ssh_user=vagrant ansible_ssh_pass=vagrant" \
-e "dc_main=my-domain dc_string=dc=my-domain,dc=com" \
-e "ldap_admin_id=admin ldap_admin_password=secret" \
-e "ldap_user_id=willyhu ldap_user_password=secret" 
```

## License

MIT / BSD

## Author Information

willyhu.tw@gmail.com

