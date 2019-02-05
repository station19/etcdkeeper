基于 源项目 https://github.com/ichiranakita/etcdkeeper 修改而来
##### 1, 安装golang
```
yum install golang -y
```
##### 2,编译go执行文件
```
git clone https://github.com/station19/etcdv2-webui.git
cd etcdv2-webui

# 修改IP地址和端口 (etcdkeeper启动IP和端口)
vim httpserver.go
# host := flag.String("h","0.0.0.0","host name or ip address")
# port := flag.Int("p", 8080, "port")

#修改 etcdkeeper/index.html  (8080端口为etcdkeeper启动IP和端口,2379端口为 etcd的IP <<etcd IP为 nginx集群etcd的代理IP>>)
vim etcdkeeper/index.html
# var serverBase = "http://10.0.0.109:8080/request?url=";
# var etcdBase = "http://10.0.0.109:2379/v2/keys";
 
cd etcdkeeper
go build httpserver.go
#启动
./httpserver
```

##### 访问 
```
http://10.0.0.109:8080/etcdkeeper
```

##### 设置
```
左侧 右键选择 create node
Name:	127.0.0.1:555
Dir:	FALSE
TTL:	 (此处不填 留空, 填写后会导致 数据无故消失,保存后 默认值是 0)
Value:	{"weight":1, "max_fails":2, "fail_timeout":30, "down":1}
```
