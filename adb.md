---
title: adb (Android Debug Bridge)
category: CLI
layout: 2017/sheet
weight: -1
authors:
  - github: ZackNeyland
updated: 2018-03-06
---

### 基本服务

| Command                           | Description                           |
| ---                               | ---                                   |
| `adb devices`                     | 列出连接的设备                         |
| `adb devices -l`                  | 列出连接的设备和种类                    |
| ---                               | ---                                   |
| `adb root`                        | 使用root权限重新启动                    |
| `adb start-server`                | 启动adb服务器                          |
| `adb kill-server`                 | 结束adb服务器                          |
| `adb remount`                     | 重新调用具有读/写访问权限的文件系统      |
| `adb reboot`                      | 重新启动设备                           |
| `adb reboot bootloader`           | 将设备进入刷机模式                      |
| `adb disable-verity`              | 将设备进入刷机模式                      |

可以在`adb`之后指定`wait-for-device`，以确保在连接设备后命令将运行.

`-s`可用于在连接多个设备时将命令发送到特定设备.

#### 举个栗子

```
$ adb wait-for-device devices
 List of devices attached
 somedevice-1234 device
 someotherdevice-1234 device
```

```
$ adb -s somedevice-1234 root
```

### 日志输出

| Command                              | Description                            |
| ---                                  | ---                                    |
| `adb logcat`                         | 开始将日志消息打印到stdout               |
| `adb logcat -g`                      | 显示当前日志缓冲区大小                   |
| `adb logcat -G <size>`               | 设置缓冲区大小(K或M)                    |
| `adb logcat -c`                      | 清除日志缓冲区                          |
| `adb logcat *:V`                     | 启用所有日志消息(verbose)               |
| `adb logcat -f <filename>`           | 转储到指定的文件                        |

#### 举个栗子
```
$ adb logcat -G 16M
$ adb logcat *:V > output.log
```

### 文件管理

| Command                              | Description                       |
| ---                                  | ---                               |
| `adb push <local> <remote>` | 将本地文件复制到远程设备  |
| `adb pull <remote> <local>` | 将远程设备文件复制到本地 |

#### 举个例子

```
$ echo "This is a test" > test.txt
$ adb push  test.txt /sdcard/test.txt
$ adb pull /sdcard/test.txt pulledTest.txt
```

### 远程脚本

| Command                                | Description                                                           |
| ---                                    | ---                                                                   |
| `adb shell <command>`                  | 在设备上运行指定的命令（大多数unix命令在这里工作）                        |
| `adb shell wm size`                    | 显示当前屏幕分辨率                                                     |
| `adb shell wm size WxH`                | 将分辨率设置为WxH                                                      |
| `adb shell pm list packages`           | 列出所有已安装的包                                                     |
| `adb shell pm list packages -3`        | 列出所有已安装的第三方包                                                |
| `adb shell monkey -p app.package.name` | 启动指定的包                                                           |
