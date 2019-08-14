# linux_squid
squid 多ip，高匿 <br>

# squid 安装 
https://www.tecmint.com/install-squid-in-ubuntu/<br>
$ sudo apt update<br>
$ sudo apt -y install squid<br>
$ sudo systemctl start squid<br>
$ sudo systemctl enable squid<br>
$ sudo systemctl status squid<br>
$ sudo vim /etc/squid/squid.conf<br>
$ sudo systemctl restart squid<br>


# 多ip代理
https://tastyplacement.com/squid-proxy-multiple-outgoing-ip-addresses <br>

# Squid normally listens to port 3128 
网段可以改成具体网址 <br>
http_port 67.xxx.108.128:3128 name=3128 <br>
http_port 67.xxx.108.79:3129 name=3129<br>
http_port 67.xxx.108.80:3130 name=3130<br>
http_port 67.xxx.108.221:3131 name=3131<br>
http_port 208.xxx.34.154:3132 name=3132<br>
http_port 208.xxx.34.32:3133 name=3133<br>

acl tasty3128 myportname 3128 src 24.xxx.210.0/24<br>
http_access allow tasty3128<br>
tcp_outgoing_address 67.xxx.108.128 tasty3128<br>
<br>
acl tasty3129 myportname 3129 src 24.xxx.210.0/24<br>
http_access allow tasty3129<br>
tcp_outgoing_address 67.xxx.108.79 tasty3129<br>
<br>
acl tasty3130 myportname 3130 src 24.xxx.210.0/24<br>
http_access allow tasty3130<br>
tcp_outgoing_address 67.xxx.108.80 tasty3130<br>
<br>
acl tasty3131 myportname 3131 src 24.xxx.210.0/24<br>
http_access allow tasty3131<br>
tcp_outgoing_address 67.xxx.108.221 tasty3131<br>
<br>
acl tasty3132 myportname 3132 src 24.xxx.210.0/24<br>
http_access allow tasty3132<br>
tcp_outgoing_address 208.xxx.34.154 tasty3132<br>
<br>
acl tasty3133 myportname 3133 src 24.xxx.210.0/24<br>
http_access allow tasty3133<br>
tcp_outgoing_address 208.xxx.34.32 tasty3133<br>

# 变量，参数定义
https://www.centos.bz/2018/08/squid%e4%bb%a3%e7%90%86%e6%9c%8d%e5%8a%a1%e7%9a%84acl%e8%ae%bf%e9%97%ae%e6%8e%a7%e5%88%b6%e3%80%81%e6%97%a5%e5%bf%97%e5%88%86%e6%9e%90%e5%8f%8a%e5%8f%8d%e5%90%91%e4%bb%a3%e7%90%86%ef%bc%884-1%e7%89%88/<br>

# Squid 配置高匿代理
https://xnathan.com/2017/03/01/squid-anony-proxy/ <br>

实现方法比较简单，只需要将如下配置加入到配置文件/etc/squid/squid.conf末尾即可。<br>

request_header_access Via deny all<br>
request_header_access X-Forwarded-For deny all<br>
request_header_access From deny all<br>

也可以参考这个网址：<br>
https://serverfault.com/questions/241918/how-can-i-prevent-squid-from-being-detected   <br>


