# 插件开发说明

## 添加包

在 `packages/<名称>/` 下创建包，并在包的 README 中说明功能、适用的 DSH 版本、安装方式和使用方法。按包的实际需要提供 `build`、`test` 和 `typecheck` 脚本；根目录的同名命令会运行这些脚本。

DSH 的插件模块和安装用的 bundle 是不同的概念。可安装的 bundle 需要在自己的 `package.json` 中声明 `dsh.bundle.patch`，并携带对应的配置文件和运行所需文件。普通共享库不需要声明 `dsh.bundle`。具体格式以 [DSH 官方打包教程](https://github.com/deepseek-ai/deepseek-harness/blob/master/docs/user/develop/basic/publish.md) 为准。

## 打包和安装

开发时可以为具体 bundle 使用 `pnpm pack`，再用 `dsh plugin --profile <profile> add <生成的 tgz 路径>` 安装验证。发布到 npm 或从 Git 安装时，应分别验证产物、依赖和目标 DSH 版本；从 Git 安装的构建步骤不能依赖用户本地存在整个工作区。

DSH 官方插件市场支持在索引中指定 Git 仓库、提交和包所在子目录。市场安装和直接使用 `dsh plugin add` 是不同入口，应分别验证，具体格式见 [官方插件市场文档](https://deepseek-harness.github.io/deepseek-harness/en/guide/plugin-market)。
