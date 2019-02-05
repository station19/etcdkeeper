##### 1, 安装golang
```
yum install golang -y
```
##### 2,编译go执行文件
```
# 修改IP地址和端口 etcdkeeper 
# host := flag.String("h","0.0.0.0","host name or ip address")
# port := flag.Int("p", 8080, "port")

cd etcdkeeper
go build httpserver.go
#启动
./httpserver
```

##### 访问 
```
http://10.0.0.109:8080/etcdkeeper
```
