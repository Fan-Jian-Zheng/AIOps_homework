- 创建 tcp_client 镜像
- ```bash
  docker build -t client:test . -f Dockerfile_client 
  ```
- 创建 tcp_server 镜像
- ``` bash
  docke build -t server:test . -f Dockerfile_server
  ```
- ![镜像构建成功](./镜像大小.png)
- 运行 tcp_server 容器
- ```bash
  docker run -p 3333:3333 --name server server:test
  ```
- ![tcp_sercer 运行成功](./tcp_server接收信息.png)
- 运行 tcp_client 容器
- ```bash
  docker run --network cotainer:server client:test
  ```
- ![tcp_client 运行成功](./tcp_client发送信息.png)