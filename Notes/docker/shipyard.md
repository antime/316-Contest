# Shipyard 的一些使用

```
#curl -sSL https://shipyard-project.com/deploy | bash -s                                                        // 下载自动化部署脚本
#curl -sSL https://shipyard-project.com/deploy | ACTION=node DISCOVERY=etcd://192.168.56.103:4001 bash -s       // 添加新节点到主节点上，192.168.56.103是主节点的IP地址
```

- 检查端口占用

```
$sudo netstat | grep 端口号
```

- 查看具体哪个程序占用端口

```
$sudo lsof -i :端口号
```
