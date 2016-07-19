### 常用命令
1.解压文件
```
.tar.gz   格式解压为 tar  -zxvf  xx.tar.gz
.tar.bz2  格式解压为 tar  -jxvf  xx.tar.bz2
```

2.配置网路（简单）
```
ifconfig eth0 192.168.1.15 netmask 255.255.255.0  

ifconfig eth0:1 192.168.1.7 broadcast  192.1681.255 netmask 255.255.255.0  

ifconfig eth0:2 192.168.1.10 broadcast  192.1681.255 netmask 255.255.255.0
```

/usr/bin/mysqladmin -u root password 'new-password'
/usr/bin/mysqladmin -u root -h localhost.localdomain password 'new-password'
/usr/bin/mysql_secure_installation
