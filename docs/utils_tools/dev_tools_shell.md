# 开发工具 - 常用 shell 命令/脚本

本文记录在开发过程中常用的 shell 命令及脚本


## 基本 shell 操作

## 软件/命令查看手册 man (Manual, 男人的手册)

- man

### 文件/路径管理

- 创建文件/文件夹 touch,mkdir,echo

- 查看文件 cat,hard,tail

- 文件/文件夹移动 && 复制 mv, cp

- 文件/文件夹删除 rm


### Ubuntu 软件包管理 - apt

- 更新软件仓库

	```shell
	**[terminal]
	**[command sudo apt update]
	```

- 更新软件

	```shell
	**[terminal]
	**[command sudo apt upgrade]
	```

- 移除无效软件包
	```shell
	**[terminal]
	**[command sudo apt autoremove]
	```

## 常用软件包

### 解/压缩文件管理 - tar && zip

### 文本编辑器 vi,vim,nano

#### vi/vim 使用

vim 为 vi 升级版本,故这里以 vim 为例

- 使用 vim 创建/编辑文件文件

	```shell
	**[terminal]
	**[command vim [file_path].txt]
	```
vim 打开文件是默认处于命令模式













