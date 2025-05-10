# FRP 服务器部署包

这是一个 FRP（Fast Reverse Proxy）服务器的自动化部署包，帮助你快速在服务器上部署和配置 frps 服务。

## 目录内容

- `bin/frps`: FRP 服务器端可执行文件
- `frps.toml`: FRP 服务器配置文件
- `install_frps.sh`: 自动安装脚本
- `VERSION`: 版本信息
- `frp部署指南.md`: 详细使用文档
- `frp-config.html`: FRP 客户端配置生成界面
- `start-config-ui.py`: 启动配置界面的 Python 脚本

## 快速开始

1. 解压部署包：
```bash
tar -zxvf frps-deploy.tar.gz
cd frps-deploy
```

2. 运行安装脚本：
```bash
sudo ./install_frps.sh
```

3. 安装完成后，脚本会显示相关的连接信息。

## 手动安装

如果您不想使用自动安装脚本，也可以按照以下步骤手动安装：

1. 将 `bin/frps` 复制到您的系统路径：
```bash
sudo cp bin/frps /usr/local/bin/
sudo chmod +x /usr/local/bin/frps
```

2. 创建配置目录并复制配置文件：
```bash
sudo mkdir -p /etc/frp
sudo cp frps.toml /etc/frp/
```

3. 手动启动 frps：
```bash
frps -c /etc/frp/frps.toml
```

## Web配置界面

本包还包含一个简易的Web配置工具，帮助您生成frpc（客户端）配置。

运行以下命令启动Web配置工具：
```bash
python3 start-config-ui.py
```

然后在浏览器中访问 http://localhost:8080 即可使用配置工具。

## 注意事项

1. 安装脚本中默认的认证令牌是 "12345678"，请务必在部署后修改为更安全的值。
2. 默认的管理面板登录凭据是 admin/admin，请在生产环境中修改这些默认值。
3. 确保您的服务器防火墙已放行相关端口（默认为7000和7500）。

## 下载

您可以从本仓库的[Releases](https://github.com/Gaoce8888/frp-server-deploy/releases)页面下载最新的部署包。

## 更多信息

有关 frp 的详细使用方法和高级配置，请参阅以下资源：

- [官方文档](https://gofrp.org/docs/)
- [GitHub 项目](https://github.com/fatedier/frp)

## 贡献者

该部署包基于 [fatedier/frp](https://github.com/fatedier/frp) 项目构建。