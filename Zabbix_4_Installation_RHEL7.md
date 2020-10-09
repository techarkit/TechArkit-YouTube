## Disable SELinux ##
- `vi /etc/selinux/config`
- `SELINUX=disabled`

#Save&Exit
`setenforce 0`

## Stop Firewalld Service ##
- `systemctl stop firewalld`
- `systemctl stop firewalld`
- `systemctl mask firewalld`
- `yum install httpd mariadb-server php php-cli php-common php-mestring php-mysqlnd php-xml php-bcmatch php-devel php-pear php-gd libssh2 -y`

## Edit PHP.ini file and change below values ##
- `vim /etc/php.ini`

- `memory_limit = 256M`
- `upload_max_filesize = 16M`
- `post_max_size = 16M`
- `max_execution_time = 300`
- `max_input_time = 300`
- `max_input_vars = 10000`
- `date.timezone = Asia/Kolkata`

Save&Exit

## Start Web and Database services ##
- `systemctl start httpd`
- `systemctl enable httpd`
- `systemctl enable mariadb`
- `systemctl start mariadb`
- `mysql_secure_installation`

Answer database config

## Login to mariadb and create database ##
- `mysql -u root -p`
- `create database zabbix character set utf8 collate utf8_bin;`
- `grant all privileges on zabbix.* to zabbix@localhost identified by 'zabbix';`
- `flush privileges;`
- `exit;`

## Install Zabbix Packages ##
- `yum install zabbix-server-mysq; zabbix-web-mysql zabbix-agent zabbix-apache-conf zabbix-java-gateway -y`

- `systemctl enable zabbix-server; systemctl enable zabbix-agent;`
- `systemctl start zabbix-server;`
- `systemctl start zabbix-agent;`

- `cd /usr/share/doc/zabbix-server-mysql-4.0.25/`
- `zcat create.sql.gz | mysql -u zabbix -pzabbix zabbix`

## Edit Config file and verify below values ##
- `vim /etc/zabbix/zabbix_server.conf`
- LogFile=/var/log/zabbix/zabbix_server.log
- LogFileSize=0
- PidFile=/var/run/zabbix/zabbix_server.pid
- SocketDir=/var/run/zabbix
- DBHost=localhost
- DBName=zabbix
- DBUser=zabbix
- DBPassword=zabbix
- DBPort=3066
- SNMPTrapperFile=/var/log/snmptrap/snmptrap.log
- Timeout=4
- AlertScriptsPath=/usr/lib/zabbix/alertscripts
- ExternalScripts=/usr/lib/zabbix/externalscripts
- LogSlowQueries=3000

- `systemctl restart zabbix-server`
- `systemctl restart httpd`

http://zabbix-server-ip/zabbix

- Complete setup
- Done!

- Default Zabbix Credentails
- UserName: Admin
- Password: zabbix
