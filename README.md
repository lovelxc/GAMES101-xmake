# GAMES101作业 xmake 版本

理论上跨平台，只测试过 Windows，Linux/MAC 未测试

如果第三方库没有预编译版本，Xmake 会手动拉取依赖源码并行编译

# 快速开始

1. 安装 C++ 编译工具链，如 MSVC(visual studio)
2. 安装 C++ 的 构建系统 + 包管理： [Xmake](https://xmake.io/#/zh-cn/guide/installation)
3. 下载所有作业源码

```bash
git clone https://github.com/star-hengxing/GAMES101-xmake.git
```

4. 进入作业目录测试，比如

```bash
cd src/Assignment1
xmake -y
xmake run
```

如果下载包失败请看[FQA](#fqa)

# 注意事项

* 所有作业文档在 doc 目录
* 所有模型在 models 目录
* 每个作业**运行环境**都在自己作业目录下，有需要可以在 xmake.lua 里修改`set_rundir`的路径

# IDE 支持

## vscode

安装插件`clangd`和`codelldb`.

在作业目录创建以下文件`.vscode/settings.json`，然后写入
```json
{
    "clangd.arguments": [
        "--compile-commands-dir=.vscode",
    ],

    "xmake.debugConfigType": "codelldb",
}
```

## visual studio

```bash
xmake project -k vsxmake -m "debug,release
```

更多请查看 xmake 文档 -> https://xmake.io/#/zh-cn/plugin/more_plugins

# FQA

Q: xmake 下载包失败怎么办  
A: 查看文档[使用远程包 - xmake](https://xmake.io/#/zh-cn/package/remote_package?id=%e8%bf%9c%e7%a8%8b%e5%8c%85%e4%b8%8b%e8%bd%bd%e4%bc%98%e5%8c%96)

Q: opencv 没有下载预编译版本怎么办  
A: 可能需要更新你的 msvc 版本

Q: 编译失败怎么办  
A: 执行`xmake -vD` ，查看详细输出信息

# 参考

1. [https://github.com/slicol/Games101-Homework-Win](https://github.com/slicol/Games101-Homework-Win)
