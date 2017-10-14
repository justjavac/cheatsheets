---
title: OS X
---

### 启动项的位置

    /System/Library/LaunchAgents/
    /System/Library/LaunchDaemons/
    /Library/LaunchAgents/
    /Library/LaunchDaemons/

### 隐藏桌面图标

    defaults write com.apple.finder CreateDesktop -bool false
    killall Finder

### 自动隐藏Dock上的其他窗口

    defaults write com.apple.dock single-app -bool TRUE
    killall Dock

    defaults delete com.apple.dock single-app
    killall Dock

### 刷新DNS

    killall -HUP mDNSResponder   # 10.8+
    dscacheutil -flushcache      # 10.7 below

### 关闭Spotlight

    sudo vim /etc/hostconfig  # change SPOTLIGHT=-YES- to SPOTLIGHT=-NO-
    mdutil -i off /
