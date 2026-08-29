# Island Survival - Docker部署配置

## 开发环境Dockerfile
```dockerfile
FROM unity/editor:2022.3.20f1

WORKDIR /app
COPY . /app

RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip \
    && rm -rf /var/lib/apt/lists/*

RUN pip3 install pillow

EXPOSE 20000

CMD ["unity", "-batchmode", "-quit", "-projectPath", "/app/源码/Unity", "-executeMethod", "FullBuildPipeline.BuildWebGL"]
```

## docker-compose.yml
```yaml
version: '3.8'

services:
  unity-builder:
    build: .
    volumes:
      - ./源码:/app/源码
      - ./Builds:/app/Builds
    environment:
      - UNITY_LICENSE=${UNITY_LICENSE}
      - UNITY_EMAIL=${UNITY_EMAIL}
      - UNITY_PASSWORD=${UNITY_PASSWORD}
  
  web-server:
    image: nginx:alpine
    ports:
      - "8080:80"
    volumes:
      - ./Builds/WebGL:/usr/share/nginx/html:ro
    depends_on:
      - unity-builder
```

## 使用方式
```bash
# 构建并运行
docker-compose up --build

# 查看构建日志
docker-compose logs -f unity-builder

# 访问游戏
open http://localhost:8080
```

---

## GitHub Actions CI/CD

### 触发条件
- Push到main/master分支
- 手动触发（workflow_dispatch）
- Release发布时

### 流程
1. 检出代码
2. 安装Unity
3. 运行测试
4. 构建WebGL
5. 上传Artifact
6. 创建Release

---

## 本地开发流程

### 1. 环境准备
```bash
# 安装Unity Hub
# 安装Unity 2022.3.20f1
# 克隆项目到F:/FGame
```

### 2. 打开项目
```bash
# Windows
start "" "F:\FGame\源码\Unity"

# 或
Unity Hub → Open → F:/FGame/源码/Unity
```

### 3. 自动搭建场景
```
Unity Editor → IslandSurvival → 自动搭建第1章场景
```

### 4. 测试游戏
```
点击 Play 按钮
WASD移动 | 鼠标攻击 | B建造 | 空格下一章
```

### 5. 构建发布
```
Unity Editor → IslandSurvival → 完整构建流程
```
