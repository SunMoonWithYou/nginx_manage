# Nginx Manager

一个交互式 Nginx 管理脚本，支持环境初始化、站点管理、SSL 证书配置、服务重启与深度卸载。

## 功能

- **环境初始化**：自动安装 Nginx、Certbot、OpenSSL，修复常见配置问题，放行 80/443 端口
- **站点管理**：添加站点、删除站点、查看已启用站点列表
- **SSL 支持**：
  - 自动申请 Let's Encrypt 证书
  - 粘贴自定义证书与私钥
  - 生成自签证书
- **服务管理**：一键重启 Nginx
- **深度卸载**：彻底清除 Nginx 及相关配置、证书和定时任务

## 一键运行

将 `yourname/yourrepo` 替换为你的 GitHub 用户名和仓库名。

### 使用 curl

```bash
curl -fsSL https://raw.githubusercontent.com/SunMoonWithYou/nginx_manage/main/install.sh | sudo bash
```

### 使用 wget

```bash
wget -qO- https://raw.githubusercontent.com/SunMoonWithYou/nginx_manage/main/install.sh | sudo bash
```

> 如果默认分支不是 `main`，请将命令中的 `main` 替换为 `master` 或其他分支名。

## 使用说明

脚本需要 root 权限运行。运行后会显示交互菜单：

```
1. 环境初始化
2. 站点列表
3. 添加站点
4. 删除站点
5. 重启服务
6. 深度卸载
0. 退出
```

- **环境初始化**：首次使用建议先执行，自动安装并配置好 Nginx 环境
- **添加站点**：输入域名，选择 SSL 方式，脚本会自动生成配置并启用站点
- **删除站点**：输入要删除的域名，自动移除配置并重载 Nginx
- **深度卸载**：会删除 `/etc/nginx`、`/var/www`、`/etc/letsencrypt` 等目录，请谨慎操作

## 注意事项

- 请确认远程脚本来源可信后再执行
- 脚本会修改系统 Nginx 配置，可能影响现有站点
- 深度卸载不可逆，操作前请备份重要数据
- 建议在全新或测试环境中使用，生产环境请先评估影响

## License

MIT
