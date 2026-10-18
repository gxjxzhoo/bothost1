# app-ws (v10)

VLESS / Trojan over WebSocket，Python 版与 Node 版功能一致。

## 目录
- `python/` app.py + index.html + Dockerfile + requirements.txt
- `node/`   index.js + index.html + Dockerfile + package.json (镜像内已装好 ws)
- `.github/workflows/image-python.yml` 改动 python/ 时构建
- `.github/workflows/image-node.yml` 改动 node/ 时构建
- 都可手动触发，amd64/arm64

## 镜像
- `ghcr.io/gxjxzhoo/python1:latest` / `gxjxzhoo/python1:latest`
- `ghcr.io/gxjxzhoo/node1:latest`   / `gxjxzhoo/node1:latest`

## 工作流需要的 Secrets
- `PRIVATE_REPO_TOKEN`：读取 gxjxzhoo/env-config 的 .env（DOCKERHUB_TOKEN、DOCKERHUB_USERNAME 自动加载）

## 运行
```
docker run -d -p 3000:3000 -e UUID=xxxx -e DOMAIN=xx.com \
  ghcr.io/gxjxzhoo/python1:latest
```
脚本内保留原变量默认值，环境变量可覆盖。
