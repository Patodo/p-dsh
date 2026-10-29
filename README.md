# p-dsh

DSH 插件仓库。多个插件可以在同一个仓库中开发，并按需要分别打包和发布。

## 目录

```text
p-dsh/
├── docs/                  # 开发与发布说明
├── packages/              # 插件、bundle 或共享代码包
├── package.json           # 工作区命令
└── pnpm-workspace.yaml    # pnpm 工作区配置
```

仓库目前只有基础结构，还没有可安装的插件。

## 开发

需要 Node.js 22.13 或更高版本，以及 pnpm 11.7.0。

```sh
pnpm install
pnpm build
pnpm test
pnpm typecheck
```

后三个命令会执行各工作区包中存在的同名脚本；没有包或没有对应脚本时不会执行任何检查。新增插件、打包和安装的约定见 [插件开发说明](docs/plugin-development.md)。

## 参考

- [DSH 插件打包和安装](https://github.com/deepseek-ai/deepseek-harness/blob/master/docs/user/develop/basic/publish.md)
- [DSH 插件市场](https://deepseek-harness.github.io/deepseek-harness/en/guide/plugin-market)
