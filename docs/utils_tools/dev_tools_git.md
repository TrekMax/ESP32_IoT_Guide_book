# 开发工具 - git 命令/脚本

本文记录在开发过程中 git 常用的命令/脚本

## git 简介 && 了解版本控制管理

## 安装 git && git 理论知识

### git 工作空间 && 版本库 && 暂存区

### 安装 git && 及相关配置

1. 安装 git

    - Windows

        [**git 官网**](https://git-scm.com) 下载安装包


    - Linux(Ubuntu)

        ```shell
        sudo apt install git -y
        ```

    - Mac OS

        等我下单 Macbook Pro 再说🤣

2. git 配置

 - git 中文显示

    在 Windows 上使用 `git status` 时,会出现中文路径显示为 `Unicode` 编码, 使用下面命令解决

    ```shell
    git config --global core.quotepath false
    ```

 - git commit 配置

    配置 `commit` 作者信息
    ```shell
    git config --global user.name "QinYUN575" # "" 内设置为自己的用户名
    git config --global user.email "QinYUN575@Gmail.com" # “” 内设置为自己的邮箱
    ```

- 推荐学习书籍/网站

## git 哲学 && 设计

## 版本控制管理

## 基本 git 使用

- 初始化 git init, git 初始化 repstory 仓库

- 克隆 git clone, 克隆仓库

- git status

- git 分支切换

    ```bash
    git branch -a # 列出所有分支
    git checkout [branch name] # 检出所有分支
    git submodule update --init --recursive # 递归初始化更新子模块
    ```

    暂存数据
    ```bash
    git stash
    ```

    ```bash
    git stash pop
    git stash apyle
    ```

## 进阶 git 使用


## 高级 git 使用

---

## git 相关问题


----

参考

> [《git-stash用法小结》](https://www.jianshu.com/p/1c7ecc8d3dfb)

> [《》](https://backlog.com/git-tutorial/cn/intro/intro3_1.html)