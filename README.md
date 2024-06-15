# VLLM + Open-WebUI Deployment Guide

### 步骤：

1. **安装Docker**：确保你的系统上已经安装了Docker。如果没有，请从[Docker官网](https://www.docker.com/get-started)下载并安装。

2. **拉取和切换目录**：
   ```bash
   git clone https://github.com/GeeseDream/vllm-openwebui.git
   cd vllm-openwebui
   ```

3. **启动服务**：使用Docker Compose启动服务：
   ```bash
   docker-compose up -d
   ```
   国内可以编辑.env文件打开HF_MIRROR注释，加速下载模型文件。
   这个命令会：
   - 启动基于VLLM框架的模型服务，充分利用GPU性能。
   - 启动Open-WebUI作为前端界面，连接到模型服务提供用户交互。

4. **访问Open-WebUI**：通过浏览器访问 `http://localhost:3000` 或者 `http://your-host-ip:3000` 来打开Open-WebUI界面。

### 注意事项：

- **API密钥安全**：确保替换掉`OPENAI_API_KEY`为一个安全的值，并避免将实际的密钥暴露在公共代码库或不安全的环境中。

### 遇到问题时：

- **检查日志**：如果遇到任何问题，请使用 `docker logs <container_name>` 命令查看容器的日志。