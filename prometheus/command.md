# commands

### docker安装和管理

#### 安装

docker run --name prometheus -d -p 127.0.0.1:9090:9090 quay.io/prometheus/prometheus

#### 管理

docker start prometheus 启动服务
docker stats prometheus 查看 prometheus 状态
docker stop prometheus 停止服务
