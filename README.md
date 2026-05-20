# github_vps

在 GitHub 上申请免费的 VPS。

 这是什么原理？
简单来说：GitHub Codespaces 本质上是一个基于 Debian/Ubuntu 的云开发环境（虚拟机）。

我们只需要在这个虚拟机里执行一条命令，就能拉起一个 Windows 11 容器，然后通过端口转发链接（设置成 Public 或者装个内网穿透工具如 ngrok）直接远程访问。就这样，GitHub 免费送你的高配 VPS，瞬间变成了一台能跑 Win11 的云电脑！

✅ 为什么这玩意儿这么香？
优势
说明
🆓 完全免费
GitHub 官方提供，不花一分钱
💪 配置给力
最高可选 4核16GB 内存
🧹 纯净系统
没有国产云厂商那种臃肿预装软件
🌐 网络自由
访问速度极快，震惊到了
⚡ 网速爆炸
GitHub 基础设施，速度快到震惊
🤖 Copilot 加持
自带 AI 编程助手，写代码如有神助
🛠️ 保姆级教程，一步一步来
第一步：Fork 仓库
先打开这个项目，点击右上角的 Fork 按钮，把仓库复制到你自己的账号下：

👉 https://github.com/1061700625/github_vps

Fork 仓库
Fork 仓库
第二步：进入 Codespaces 界面
Fork 完成后，点击页面左上角的 ☰ 三条横线，切换到 Codespaces 标签页。

切换 Codespaces
切换 Codespaces
第三步：新建 Codespace
点击 "New codespace"（新建 Codespace）按钮。

新建 Codespace
新建 Codespace
第四步：选择配置
选择你刚才 Fork 的那个仓库，然后在下方配置中选择 4-Core（4核）的规格，性能更强，体验更丝滑！

选择 4核配置
选择 4核配置
第五步：启动 Win11 容器
进入 Codespaces 后，底部会自动打开终端。输入以下命令：

bash start.sh
执行 start.sh
执行 start.sh
第六步：获取访问链接
等待命令执行，当终端出现端口转发链接时，把鼠标放上去，稍等片刻会出现 "Open in Browser"（在浏览器中打开） 的提示，点击它！

端口转发链接
端口转发链接
第七步：安装 Windows 11
此时你会进入 Windows 11 的安装界面，接下来就是熟悉的装系统流程了。

⚠️ 注意：这一步需要耐心等待，安装过程会比较久，可以去泡杯咖啡 ☕

Win11 安装界面 1
Win11 安装界面 1
Win11 安装界面 2
Win11 安装界面 2
Win11 安装中
Win11 安装中
第八步：进入桌面，安装成功！
当当当！看到熟悉的 Win11 桌面，你就成功了！

Win11 桌面
Win11 桌面
第九步：验货！测速 + 测硬盘 + 测 Copilot
装好了当然要跑个分看看：

• 硬盘大小：充足，完全够用
• 网速测试：这速度真的震惊到我了，GitHub 的基础设施不是盖的！
• Copilot AI：写代码、问问题，AI 随叫随到
测速和 Copilot
测速和 Copilot
第十步：手机也能玩！
更骚的是，手机也能访问这台 Win11！

下载 GitHub 手机客户端，随时随地启动 Codespace，就算没有电脑，你也能拥有一台免费的高配云主机。

躺在床上用手机操控 Win11，这体验简直不要太好 📱💻

📝 总结
这套方案的核心就是利用 GitHub Codespaces 免费的开发环境配额，通过 Docker 容器化技术跑 Windows 11，再通过端口映射实现远程桌面访问。

适合场景：

• 临时需要一台干净的 Windows 环境测试软件
• 外出时用手机/平板应急办公
• 想体验高网速、无限制的网络环境
• 白嫖党の日常胜利 ✌️
⚠️ 温馨提示：GitHub Codespaces 免费额度有限（每月 120 核·小时 / 60 小时运行时间），建议用完及时关闭，不要长时间挂机哦！


## 创建示例

### Ubuntu
<p align="center">
  <img width="512" alt="image" src="https://github.com/user-attachments/assets/93f97616-8aaf-4206-857a-5d17aed8c4d2" />
</p>

### Windows
<p align="center">
  <img width="512" alt="image" src="https://github.com/user-attachments/assets/f40bc167-62b7-4b29-91e0-15e07a76e21c" />
</p>

## 部署教程

先给脚本添加执行权限。

```bash
chmod +x start.sh
```

## Ubuntu 使用教程

### 启动 Ubuntu

```bash
bash start.sh ubuntu
```

### 默认登录信息

Web 终端：

```text
地址：http://<url>:4200
用户名：root
密码：root
```

SSH：

```text
地址：<url>:8022
用户名：root
密码：root
```

RDP：

```text
地址：<url>:3389
用户名：root
密码：root
```

### 修改 Ubuntu root 密码

启动时可以通过 `ROOT_PASSWORD` 指定 root 密码。

```bash
ROOT_PASSWORD='admin@123' bash start.sh ubuntu
```

### 连接 SSH

本地连接示例：

```bash
ssh root@localhost -p 8022
```

如果使用外部地址，将 `localhost` 替换为你的访问地址。

```bash
ssh root@<url> -p 8022
```

### 连接 RDP

```text
地址：<url>:3389
用户名：root
密码：root
```

如果你启动时设置了 `ROOT_PASSWORD`，这里的密码就是你设置的值。

### 停止 Ubuntu

```bash
bash start.sh stop ubuntu
```

## Windows 使用教程

### 启动 Windows 11

默认启动 Windows 11。

```bash
bash start.sh
```

也可以显式指定 Win11。

```bash
bash start.sh win11
```

### 默认登录信息

管理界面：

```text
地址：http://<url>:8006
```

RDP：

```text
地址：<url>:3389
用户名：MASTER
密码：admin@123
```

### 修改 Windows 登录信息

启动前可以通过环境变量修改用户名和密码。

```bash
WINDOWS_USERNAME='MASTER' WINDOWS_PASSWORD='admin@123' bash start.sh win11
```

也可以修改资源配置。

```bash
WINDOWS_RAM_SIZE='4G' WINDOWS_CPU_CORES='4' WINDOWS_DISK_SIZE='64G' bash start.sh win11
```

### 停止 Windows

```bash
bash start.sh stop win11
```

## 停止全部

如果需要同时停止 Windows 和 Ubuntu，执行：

```bash
bash start.sh stop
```

## 端口说明

| 系统      | 服务       | 端口   |
| ------- | -------- | ---- |
| Ubuntu  | Web 终端   | 4200 |
| Ubuntu  | SSH      | 8022 |
| Ubuntu  | RDP      | 3389 |
| Windows | Web 管理界面 | 8006 |
| Windows | RDP      | 3389 |

注意，Ubuntu 和 Windows 都会使用 `3389` 端口。如果需要切换系统，请先停止当前正在运行的系统。

```bash
bash start.sh stop ubuntu
```

或者：

```bash
bash start.sh stop win11
```

