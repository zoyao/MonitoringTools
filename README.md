# MonitoringTools

购物网站监控工具,目前支持路口(https://lukou.com/)

## Docker

### build
```docker
cd ./MonitoringTools/
docker build -t check:0.1 .
```

### run
```docker
docker run -d --name check -e TZ=Asia/Shanghai --network host -v /app/py_tools_config/logs:/app/logs -v /app/py_tools_config/resources:/app/resources check:0.1
```