## V2RAY 设置

### [谷歌云新增虚拟机](https://console.cloud.google.com/compute/instances?project=bold-future-283712&authuser=1&hl=zh-CN&instancessize=50)，机器选择 normal（2 个 vCPU，4 GB 内存）。

### 解析 IP

- 获取服务器 IP 后去[cloudflare 新增解析 DNS 域名](https://dash.cloudflare.com/4d151564e957fab954cf830a2e1467df/wangsitu666.top/dns),代理状态关闭。

### 虚拟机防火墙设置：

- 允许 http、https 流量
- 网络标记 ruzhan、chuzhan

### 顶层防火墙设置（VPC 网络-防火墙）：

#### 入站：

- 名称：ruzhan
- 优先级：1
- 流量方向：入站
- 对匹配项执行的操作：允许
- 目标：网络中的所有实例
- 来源过滤条件：IP 范围
- 来源 IP 地址范围：0.0.0.0/0
- 端口和协议：全部允许

#### 出站：

- 名称：chuzhan
- 优先级：1
- 流量方向：出站
- 对匹配项执行的操作：允许
- 目标：网络中的所有实例
- 来源过滤条件：IP 范围
- 来源 IP 地址范围：0.0.0.0/0
- 端口和协议：全部允许

#### 修改 root 密码：

```
sudo passwd
```

#### 安装脚本：

```
su root
apt-get install wget
wget -N --no-check-certificate -q -O install.sh "https://raw.githubusercontent.com/wulabing/Xray_onekey/main/install.sh" && chmod +x install.sh && bash install.sh

```

#### v2ray 脚本顺序

- [参考页面](https://github.com/wulabing/Xray_onekey)

### 将订阅链接 base64 转码

- https://neilwang543.github.io/mysite/

### 订阅地址修改

- https://github.com/neilwang543/subscribeUrl#readme
