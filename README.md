# MonitoringTools

Monitoring tools for online shopping website, currently supports lukou...

购物网站监控工具,目前支持路口(<https://lukou.com/>),识别到关键词采用pushdeer(<https://github.com/easychen/pushdeer.git>)进行消息推送

## Docker

### git clone
```shell
cd /tmp/
git clone https://github.com/zoyao/MonitoringTools.git
```

### config
```shell
mkdir -r /app/py_tools_config/resources
cp /tmp/MonitoringTools/resources/config.yaml /app/py_tools_config/resources/config.yaml
vim /app/py_tools_config/resources/config.yaml
```

### build
```shell
cd /tmp/MonitoringTools/
docker build -t monitoringTools:0.1 .
```

### run
```shell
docker run -d --name monitoringTools -v /app/py_tools_config/resources:/app/resources monitoringTools:0.1
```

### run debug
```shell
docker run -d --name monitoringTools -e TZ=Asia/Shanghai --network host -v /app/py_tools_config/logs:/app/logs -v /app/py_tools_config/resources:/app/resources monitoringTools:0.1
```
