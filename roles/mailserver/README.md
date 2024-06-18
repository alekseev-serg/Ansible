# Ansible role `mailserver`


An Ansible role for installing postfix/dovecot/postfix-admin/roundcube:

- Install Mailserver packages from the official Ubuntu repositories
- Create user and group vmail
- Create database for postfix admin and roundcube
- Install postfix admin
- Copy SSL Certificate
- Install and configure dovecot
- Install and configure postfix
- Install and configure roundcube

## Role Variables

### Basic configuration

| Variable                       | Default                      | Comments                                                                                                                       |
| :---                           |:-----------------------------|:-------------------------------------------------------------------------------------------------------------------------------|
| `mailserver_domain   `         | 'devdata.lan'                | Domain for mailserver                                                                                                          |
| `mailserver_mysql_root_user`                 | 'root'                       | MySQL login for root user                                                                                                      |
| `mailserver_mysql_root_password`         | 'generate-a-random-password' | MySQL password for root user                                                                                                   |
| `mailserver_mysql_user`                     | 'mailserver'                 | MySQL user for mailserver databse                                                                                              |
| `mailserver_mysql_password`                     | 'generate-a-random-password' | MySQL password for mailserver user                                                                                             |
| `mailserver_mysql_db_name`                         | mailserver                   | Databse for postfix admin                                                                                                      |
| `mailserver_ssl_cert`          | 'mailserver.crt'             | Certificate file name                                                                                                          |
| `mailserver_ssl_key`              | mailserver.key               | Key file name                                                                                                                  |
| `mailserver_ssl_ca`                   | 'mailserver_ca.crt'          | CA Certificate file name                                                                                                       |
| `mailserver_pa_version`                 | '3.3.10'         | Postfix-admin version                                                                                                          |
| `mailserver_pa_admin_user`             | 'root@devdata.lan'                 | Postfix-admin login for admin user                                                                                             |
| `mailserver_pa_admin_password`                   | 'generate-a-random-password123'           | Postfix-admin password for admin user                                                                                          |
| `mailserver_roundcuve_version`    | '1.6.5'             | Roundcube version                                                                                                              |
| `mailserver_mysql_user_roundcube`  | 'roundcube'                      | MySQL Roundcube databse user                                                                                                   |
| `mailserver_mysql_password_roundcube`                 | 'generate-a-random-password'        | MySQL Roundcube databse password                                                                                               |
| `mailserver_mysql_db_name_roundcube`                 | 'roundcubemail'                      | MySQL Roundcube databse name                                                                                                   |

## Example Playbook

Playbook example to execute role using defaults parameters and variables

```Yaml
- hosts: mariadb
  roles:
    - role:
        - mariadb
        - nginx
        - mailserver
      become: yes
```
Playbook example to execute role using somes variables

```Yaml
- hosts: mariadb
  roles:
    - role: mailserver
      become: yes
      vars:
        mailserver_domain: 'devdata.ru'
        mailserver_ssl_cert: 'devdata.crt'
        mailserver_ssl_key: 'devdata.key'
        mailserver_ssl_ca: 'devdata_ca.crt'
        mailserver_pa_admin_password: 'qpassword'
```
