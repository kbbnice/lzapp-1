查看ip： `ip addr`

查看开放的端口：` firewall-cmd --list-ports`

开放端口： firewall-cmd --zone=public --add-port=99/tcp --permanent



#### 修改服务器欢迎语

vim /etc/motd



##### VIM 卡死的情况

因为ctrl + s 在linux中是锁屏命令， 使用`ctrl + q`可以解锁。