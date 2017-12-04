---
title: GitHub pages
category: Jekyll
layout: 2017/sheet
---

## Custom domains

### 自定义域名

```sh
$ echo "foobar.com" > CNAME
$ git commit && git push
```

创建一个 `CNAME` 文件并将填写你的域名.

查看: [设置自定义域名](https://help.github.com/articles/quick-start-setting-up-a-custom-domain/) _(github.com)_

### 设置你的域名

子域名 (例如 www):
{: .-setup}

     CNAME => username.github.io

顶级域名:
{: .-setup}

     ALIAS => username.github.io

顶级域名 (替代):
{: .-setup}

    A => 192.30.252.153
    A => 192.30.252.154

## 参考
{: .-one-column}

- <https://pages.github.com>
