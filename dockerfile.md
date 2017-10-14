---
title: Dockerfile
category: Devops
layout: 2017/sheet
---

## 参考
{: .-three-column}

### 继承

```
FROM ruby:2.2.2
```

### 变量

```
ENV APP_HOME /myapp
RUN mkdir $APP_HOME
```

### 初始化

```
RUN bundle install
```

```
WORKDIR /myapp
```

### 构建中(Onbuild)

```bash
ONBUILD RUN bundle install
# when used with another file
```

### 命令

```docker
EXPOSE 5900
CMD    ["bundle", "exec", "rails", "server"]
```

## 参考
{: .-one-column}

- <https://docs.docker.com/engine/reference/builder/>
