---
title: Ansible
category: Ansible
---

{% raw %}

## 入门

### 主机与组

    $ sudo mkdir /etc/ansible
    $ sudo vim /etc/ansible/hosts

    [example]
    192.0.2.101
    192.0.2.102

### 执行 playbook

    $ ansible-playbook playbook.yml

## 任务

    - hosts: all
      user: root
      sudo: no
      vars:
        aaa: bbb
      tasks:
        - ...
      handlers:
        - ...

### 包含

    tasks:
      - include: db.yml
    handlers:
      - include: db.yml user=timmy

## 触发

    handlers:
      - name: start apache2
        action: service name=apache2 state=started

    tasks:
      - name: install apache
        action: apt pkg=apache2 state=latest
        notify:
          - start apache2

## 变量

    - host: lol
      vars_files:
        - vars.yml
      vars:
        project_root: /etc/xyz
      tasks:
        - name: Create the SSH directory.
          file: state=directory path=${project_root}/home/.ssh/
          only_if: "$vm == 0"

## 角色

    - host: xxx
      roles:
        - db
        - { role:ruby, sudo_user:$user }
        - web

    # Uses:
    # roles/db/tasks/*.yml
    # roles/db/handlers/*.yml

### 错误处理

    - name: my task
      command: ...
      register: result
      failed_when: "'FAILED' in result.stderr"

      ignore_errors: yes

      changed_when: "result.rc != 2"

### 环境变量

    vars:
      local_home: "{{ lookup('env','HOME') }}"

## 引用

  * [Intro](http://www.ansibleworks.com/docs/intro_configuration.html)
  * [Modules](http://www.ansibleworks.com/docs/modules.html)

{% endraw %}
