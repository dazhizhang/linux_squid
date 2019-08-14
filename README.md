# linux_squid
squid 多ip，高匿 <br>

# 多ip代理
https://tastyplacement.com/squid-proxy-multiple-outgoing-ip-addresses <br>

# Squid normally listens to port 3128 
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


# Squid 配置高匿代理
https://xnathan.com/2017/03/01/squid-anony-proxy/ <br>

实现方法比较简单，只需要将如下配置加入到配置文件/etc/squid/squid.conf末尾即可。<br>

request_header_access Via deny all<br>
request_header_access X-Forwarded-For deny all<br>
request_header_access From deny all<br>

也可以参考这个网址：<br>
https://serverfault.com/questions/241918/how-can-i-prevent-squid-from-being-detected   <br>


