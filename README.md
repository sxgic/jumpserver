# JumpServer

一个 shell 脚本写的跳板机，同时支持账号密码登录和密钥认证免密登录。

## 功能

1. 账号密码形式下，每次不需要单独输入密码， 即可免密登录
2. ssh 密钥形势下，可以直接登录

## 使用

### 安装 `expect`

expect 软件包包含一个通过执行脚本对话框与其它交互式程序通信的工具。安装命令如下：

```bash
    1. debian : apt install expect
    2. yum install -y tcl expect
```

仅需打开编辑此文件，在 `hostInfoDict` 配置中 设置服务器信息，如下：
```bash
    ["服务器别名"]=["认证方式（pwd/rsa） ip port 用户名 密码/密钥路径"]
```

在终端输入即可登录，例如：
```bash
    $bash jumpserver.sh
```

## 进阶用法

配置好自己的服务器信息以后，可以把 `jumpserver.sh` 脚本拷贝作为可执行脚本，操作如下

```bash
1. cp jumpserver.sh ~/bin/j2
2. vim 编辑 `~/.bashrc` 或 `~/.zshrc` 中增加别名别名 `alias j2="bash jps"`
3. 可以通过 `j2` 来使用这个跳板机程序
```
