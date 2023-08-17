# MonitoringTools

Monitoring tools for online shopping website, currently supports lukou...

购物网站监控工具,目前支持[路口网](<https://lukou.com/>),识别到关键词采用[pushdeer](<https://github.com/easychen/pushdeer.git>)进行消息推送

## 1. configuration

```shell
mkdir -r /app/monitoring-tools/resources
cp /tmp/MonitoringTools/resources/config.yaml /app/monitoring-tools/resources/config.yaml
vim /app/monitoring-tools/resources/config.yaml
```

## 2. run

### 2.1 Docker Hub

```shell
docker run -d --name monitoringTools -v /app/monitoring-tools/logs:/app/logs -v /app/monitoring-tools/resources:/app/resources zoyao/monitoring-tools:latest
```

### 2.2 Docker Build

#### git clone
```shell
cd /tmp/
git clone https://github.com/zoyao/MonitoringTools.git
```

#### build
```shell
cd /tmp/MonitoringTools/
docker build -t monitoringTools:0.1 .
```

#### run
```shell
docker run -d --name monitoringTools -v /app/monitoring-tools/resources:/app/resources monitoringTools:0.1
```

#### run debug
```shell
mkdir -r /app/monitoring-tools/logs
docker run -d --name monitoringTools -e TZ=Asia/Shanghai --network host -v /app/monitoring-tools/logs:/app/logs -v /app/monitoring-tools/resources:/app/resources monitoringTools:0.1
```
