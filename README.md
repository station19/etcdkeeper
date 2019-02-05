##### 1, 安装golang
```
yum install golang -y
```
##### 2,编译go执行文件
```
# 修改IP地址和端口 (etcdkeeper启动IP和端口)
vim httpserver.go
# host := flag.String("h","0.0.0.0","host name or ip address")
# port := flag.Int("p", 8080, "port")

#修改 etcdkeeper/index.html  (8080端口为etcdkeeper启动IP和端口,2379端口为 etcd的IP)
vim etcdkeeper/index.html
#		var serverBase = "http://10.0.0.109:8080/request?url=";
#   var etcdBase = "http://10.0.0.109:2379/v2/keys";
 
cd etcdkeeper
go build httpserver.go
#启动
./httpserver
```

##### 访问 
```
http://10.0.0.109:8080/etcdkeeper
```
