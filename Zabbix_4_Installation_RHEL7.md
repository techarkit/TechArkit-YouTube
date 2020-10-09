## Disable SELinux ##
```vi /etc/selinux/config
SELINUX=disabled```

#Save&Exit
`setenforce 0`

## Stop Firewalld Service ##
```systemctl stop firewalld

systemctl stop firewalld
systemctl mask firewalld
yum install httpd mariadb-server php php-cli php-common php-mestring php-mysqlnd php-xml php-bcmatch php-devel php-pear php-gd -y```

## Edit PHP.ini file and change below values ##
vim /etc/php.ini

memory_limit = 256M
upload_max_filesize = 16M
post_max_size = 16M
max_execution_time = 300
max_input_time = 300
max_input_vars = 10000

date.timezone = Asia/Kolkata

# Save&Exit
