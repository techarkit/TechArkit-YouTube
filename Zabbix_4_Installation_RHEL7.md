## Disable SELinux ##
`vi /etc/selinux/config`
`SELINUX=disabled`

#Save&Exit
`setenforce 0`

## Stop Firewalld Service ##
`systemctl stop firewalld`

`systemctl stop firewalld`
`systemctl mask firewalld`
`yum install httpd mariadb-server php php-cli php-common php-mestring php-mysqlnd php-xml php-bcmatch php-devel php-pear php-gd libssh2 -y`

## Edit PHP.ini file and change below values ##
`vim /etc/php.ini`

`memory_limit = 256M`
`upload_max_filesize = 16M`
`post_max_size = 16M`
`max_execution_time = 300`
`max_input_time = 300`
`max_input_vars = 10000`
`date.timezone = Asia/Kolkata`

# Save&Exit

## Start Web and Database services ##
`systemctl start httpd`
`systemctl enable httpd`
`systemctl enable mariadb`
`systemctl start mariadb`
`mysql_secure_installation`
Answer database config

## Login to mariadb and create database ##
`mysql -u root -p`
`> create database zabbix character set utf8 collate utf8_bin;`
`grant all privileges on zabbix.* to zabbix@localhost identified by 'zabbix';`
`flush privileges;`
`exit;`


