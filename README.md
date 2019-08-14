# linux_squid
squid 多ip，高匿 <br>




# Squid 配置高匿代理
https://xnathan.com/2017/03/01/squid-anony-proxy/ <br>

实现方法比较简单，只需要将如下配置加入到配置文件/etc/squid/squid.conf末尾即可。<br>

request_header_access Via deny all<br>
request_header_access X-Forwarded-For deny all<br>
request_header_access From deny all<br>

也可以参考这个网址：<br>
https://serverfault.com/questions/241918/how-can-i-prevent-squid-from-being-detected   <br>


