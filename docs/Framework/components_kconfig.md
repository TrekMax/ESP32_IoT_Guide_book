# ESP-IDF 组件(componenets) && kconfig

最新版本的 esp-idf 已经启用了 Cmake 替代之前的 GUN Make 作为默认自动构建编译流程的工具,并且esp-idf 将在 release/v5 中彻底放弃 make.

- 关于 GCC,make,cmake 大部分只使用 keill/iar 的开发工程师都不清楚,可以看下面这篇文章了解一下 [《GCC 和 cmake的关系》](https://www.zhihu.com/question/36609459/answer/89743845)


## components


makefile 组件包含

    = 是最基本的赋值

    := 是覆盖之前的值

    ?= 是如果没有被赋值过就赋予等号后面的值

    += 是添加等号后面的值


- SDK 组件 [优先级最低]

- 工程 组件 [其次]

- 特殊组件 main [最高]


