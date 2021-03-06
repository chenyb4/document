# 简介

EayunStack运维工具提供了对EayunStack环境的检测、管理功能。主要功能通过选项及子命令来实现不同功能：

## 命令格式

```
# eayunstack --help
usage: eayunstack [-h] [-o FILENAME] [-d] [-e EMAIL] COMMAND ...

EayunStack Management Tools.

optional arguments:
  -h, --help            show this help message and exit
  -o FILENAME, --output FILENAME
                        Local File To Save Output Info
  -d, --debug           Log debug message or not
  -e EMAIL, --email EMAIL
                        email address which send error log to(use commas to
                        separate multiple email address)

Commands:
  COMMAND               DESCRIPTION
    upgrade             Upgrade Management
    doctor              EayunStack Doctor
    manage              EayunStack Management
    list                List OpenStack Node
    init                EayunStack Environment Initialization
    cleanup             EayunStack Cleanup Resources
    fuel                EayunStack Fuel Management
```

>  **注意**
>
>  在不同角色的节点上执行该命令时可用的子命令不同，不可用的子命令会被隐藏。
>  例如：在fuel节点上使用"--help"查看命令帮助信息时未显示"manage"、"cleanup"子命令。

## 选项及子命令功能简介

### 选项

* -h，--help
   * 查看命令帮助信息
* -o FILENAME, --output FILENAME
   * 将命令执行结果保存到指定文件中
* -d, --debug
   * 命令执行时输出Debug信息（默认不输出Debug信息）
* -e EMAIL, --email EMAIL
   * 将命令执行时输出的"ERROR"级别的信息发送到指定邮箱

### 子命令

* fuel
   * Fuel节点备份
   * Fuel节点恢复
   * 监控平台部署
* init
   * 初始化EayunStack环境
   * 升级环境中所有节点上的 tools
* manage
   * 删除错误的Cinder卷
   * 上传AMI镜像
   * 删除错误的云主机
* list
   * 列出环境中所有OpenStack节点的信息
* doctor
   * 检测所有OpenStack节点基础环境状态
   * 检测所有OpenStack节点OpenStack组件配置及服务运行状态
   * 检测MySQL/RabbitMQ/Ceph/Pacemaker/HAProxy集群状态
   * 检测OpenStack网络（如virtual router检测）
* upgrade
   * 环境升级
* cleanup
   * 清理环境中无租户资源（涉及到资源清理，慎用！）