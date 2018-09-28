---
title: pm2
category: CLI
layout: 2017/sheet
authors: { github: "Dr-Dino" }
updated: 2018-03-15
---

### Fork模式

| Command                          | Description              |
| ---                              | ---                      |
| `pm2 start app.js --name my-api` | 启动并命名进程            |

### Cluster模式

| Command                 | Description                                                        |
| ---                     | ---                                                                |
| `pm2 start app.js -i 0` | 将根据可用的CPU启动LB(调度器)的最大进程	                              |

### 列举

| Command          | Description                                         |
| ---              | ---                                                 |
| `pm2 list`       | 显示所有进程状态                                     |
| `pm2 jlist`      | 在原始JSON中的打印进程列表                            |
| `pm2 prettylist` | 在美化的JSON中的打印进程列表                          |
| ---              | ---                                                 |
| `pm2 describe 0` | 显示特定流程相关的所有信息                            |
| ---              | ---                                                 |
| `pm2 monit`      | 监控所有流程                                         |

### 日志

| Command            | Description                               |
| ---                | ---                                       |
| `pm2 logs [--raw]` | 以流方式显示所有进程日志	                   |
| `pm2 flush`        | 清空所有日志文件                           |
| `pm2 reloadLogs`	 | 重载所有日志                               |

### 操作

| Command           | Description                                    |
| ---               | ---                                            |
| `pm2 stop all`    | 停止所有进程                                    |
| `pm2 restart all` | 重启所有进程                                    |
| ---               | ---                                            |
| `pm2 reload all`  | 0秒重启（对于NETWORKED应用程序）	               |
| ---               | ---                                            |
| `pm2 stop 0`      | 停止特定ID的进程                                |
| `pm2 restart 0`   | 重启特定ID的进程                                |
| ---               | ---                                            |
| `pm2 delete 0`    | 将从pm2列表中删除进程                            |
| `pm2 delete all`  | 将从pm2列表中删除所有进程                        |

### 杂项

| Command                             | Description                                                    |
| ---                                 | ---                                                            |
| `pm2 reset <process>`               | 重置元数据(重启时间...)                                          |
| `pm2 updatePM2`                     | 更新pm2内存                                                     |
| `pm2 ping`                          | 确保已启动pm2守护程序                                            |
| `pm2 sendSignal SIGUSR2 my-app`     | 将系统信号发送到脚本                                              |
| ---                                 | ---                                                            |
| `pm2 start app.js --no-daemon`      | 如果pm2守护程序y已经不存在，在前台运行pm2守护程序	                 |
| `pm2 start app.js --no-vizion`      | 跳过vizion特性（版本控制）                                       |
| `pm2 start app.js --no-autorestart` | 禁止自动重启应用程序                                             |
