# syncthing-lzcapp

[Syncthing](https://github.com/syncthing/syncthing) 的懒猫微服 LPK 打包（镜像模式，LPK v2）。

- 包名：`community.lazycat.app.syncthing`
- 上游镜像：`docker.io/syncthing/syncthing`（官方镜像）
- 版本源：镜像 tag（`v2.1.7` → `2.1.7`）
- 发布目标：喵喵商店（私有/社区商店）

## 网络

- GUI（Web 界面）：应用 upstreams 8384
- 同步协议：ingress 22000 TCP + UDP
- 本地发现：ingress 21027/UDP

官方推荐 host 网络模式（LAN 直连优化），LPK 内改用 ingress 端口映射，
远程设备添加本实例时使用懒猫设备地址 + 22000 端口。

## 免密登录

Syncthing Web GUI 首次访问即要求创建管理员账号，通过部署参数
（`simple-inject-password` + 登录页自动填充）配置初始凭据。
