---
title: composer
category: CLI
layout: 2017/sheet
weight: -1
authors:
  - github: benolot
updated: 2018-03-06
description: |
  Basic guide on how to use Composer, the PHP Package manager.
---

您安装的所有composer命令，可能需要在composer的安装文件夹中使用 `php composer.phar`，而不是普通的 `composer`.

### 包管理

| Command                                | Description                                                  |
| ---                                    | ---                                                          |
| `composer install`                     | 安装composer.json中的所有内容                                  |
| ---                                    | ---                                                          |
| `composer install laravel`             | 安装包                                                        |
| `composer install laravel --dry-run`   | 模拟安装并显示将会发生什么                                      |
| `composer install laravel --no-scripts`| 跳过 composer.json 文件中定义的脚本                             |

### 更新

| Command                   | Description                          |
| ---                       | ---                                  |
| `composer update`         | 更新所有的包                          |
| ---                       | ---                                  |
| `composer update laravel` | 更新某个包                            |
| `composer update vendor/*`| 更新文件夹下所有的包                   |
| `composer update --lock`  | 仅更新 lock 文件的 hash，而不更新任何包 |



### 依赖

| Command                          | Description                                                 |
| ---                              | ---                                                         |
| `composer require laravel`.      | 将新包添加到 `composer.json` 并安装它                         |
| ---                              | ---                                                         |
| `composer require laravel --dev` | 将新包添加到 `require-dev ` 并安装它                          |

### 移除

| Command                   | Description                                                 |
| ---                       | ---                                                         |
| `composer remove laravel` | 在composer.json中移除新的包并卸载它                           |
