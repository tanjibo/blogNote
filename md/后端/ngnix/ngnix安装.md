### ngnix 安装
##### 官网:(http://nginx.org)
---

**1.首先确认是不是有安装编译包和一些依赖包**

  ```
  yum -y install gcc gcc-c++ openssl openssl-devel zlib zlib-devel autoconfig automake pcre pcre-devel
  pcre  用于rewrite 重写
  ```

**2.创建运行ngnix 的用户**
```
 groupadd www
 useradd -M -s /sbin/nologin -g www www
```


**3.下载 安装 ngnix**
```
  # wget http://ngnix.org/download/nginx-1.9.2.tar.gz
  # tar zxvf nginx-1.9.2.tar.gz
  # cd  nginx-1.9.2
# ./configure --prefix=/usr/local/ngnix(安装目录)             --with-pcre --user=www --group=www --with-http_stub_status_module --with-http_ssl_module
  # make && make install
```

**4.关闭centos防火墙**
```
 service iptables stop
 chkconfig --level 35 iptables off (永久关闭)
```

5.启动ngnix
```
 检查nginx配置文件语法有没有问题
 # /usr/local/nginx/sbin/nginx -t
 启动
 # /usr/local/nginx/sbin/nginx
 重启
 # /usr/local/nginx/sbin/nginx -s reload
 完美停止
 # kill -QUIT `cat /var/run/nginx.pid`
 快速停止
 kill -TERM`cat /var/run/nginx.pid`
 或者
 kill -INT`cat /var/run/nginx.pid`
 完美停止工作进程
 kill -WINCH `cat /var/run/nginx.pid`

 平滑启动
 kill -HUP `cat /var/run/nginx.pid`
  强制停止
 pkill -9 nginx
 #
```
##常用命令
```
 /usr/local/nginx/sbin/nginx -v 查看版本
 /usr/local/nginx/sbin/nginx -V  查看编译的参数和模块
```
