# 与网络无关的Linux

* @Author: cpu\_code
* @Date: 2020-07-12 14:09:20
* @LastEditTime: 2020-07-12 21:08:35
* @FilePath: \note\android\_bottom\smart\_pointer.md
* @Gitee: [https://gitee.com/cpu\_code](https://gitee.com/cpu_code)
* @Github: [https://github.com/CPU-Code](https://github.com/CPU-Code)
* @CSDN: [https://blog.csdn.net/qq\_44226094](https://blog.csdn.net/qq_44226094)
* @Gitbook: [https://923992029.gitbook.io/cpucode/](https://923992029.gitbook.io/cpucode/)

## 修改主机名

```text
vi /etc/sysconfig/network
```

```text
# 修改 HOSTNAME 一行为 (没有这行, 那就添加这一行吧)
HOSTNAME=主机名
```

```text
# 运行命令
hostname  # 主机名
```

一般还要修改 /etc/hosts 文件中的主机名。这样，无论你是否重启，主机名都修改成功

## Ret Hat Linux 启动到文字界面\(不启动 xwindow\)

```text
# x=3:文本方式  x=5:图形方式
vi /etc/inittab
id:x:initdefault:
```

## linux 的自动升级更新问题

对于 redhat，在 www.redhat.com/corp/support/errata/ 找到补丁， 6.1 以后的版本带有一个工具up2date，它能够测定哪些 rpm 包需要升级，然后自动从 redhat 的站点下载并完成安装

```text
# 升级除 kernel 外的 rpm
up2date -u
```

```text
# 升级包括 kernel 在内的 rpm
up2date -u -f
```

由于 Red Hat Network SSL 证书过期，所以应在 rhn\_register \|\| up2date 之前先执行一行 script 以更新证书：

```text
wget -q -O - https://rhn.redhat.com/help/new-cert.sh | /bin/bash
```

Debian 下升级软件：

```text
# 前提：配置好网络和 /etc/apt/sources.list，也可以用 apt-setup 设置
apt-get update
apt-get upgrade
```

## windows 下看 linux 分区的软件

```text
Paragon.Ext2FS.Anywhere.2.5.rar 

explore2fs-1.00-pre4.zip
```

## mount 用法

```text
# fat32 的分区
mount -o codepage=936,iocharset=cp936 /dev/hda7 /mnt/cdrom
```

```text
# ntfs 的分区 
mount -o iocharset=cp936 /dev/hda7 /mnt/cdrom
```

```text
# iso 文件
mount -o loop /abc.iso /mnt/cdrom
```

```text
# USB 闪存
mount /dev/sda1 /mnt/cdrom
```

```text
# 软盘
mount /dev/fd0 /mnt/floppy
```

## 在 vmware 的 LINUX 中使用本地硬盘的 FAT 分区

## 删除名为-a 的文件

```text
rm ./-a
```

## 删除名为\a 的文件

```text
rm \\a
```

## 删除名字带的/和‘\0'文件

## 删除名字带不可见字符的文件

## 删除文件大小为零的文件

## redhat 设置滚轮鼠标

