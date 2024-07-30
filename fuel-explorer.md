# 入门指南

## 要求

此项目包括前端和合约部分。开始之前，请安装以下依赖项：

- [Node.js v20.11.0 或最新稳定版](https://nodejs.org/en/)。我们建议使用 [nvm](https://github.com/nvm-sh/nvm) 来安装。
- [PNPM v8.15.7 或最新稳定版](https://pnpm.io/installation/)
- [Docker v25.0.3 或最新稳定版](https://docs.docker.com/get-docker/)
- [Docker Compose v2.24.6 或最新稳定版](https://docs.docker.com/get-docker/)
- [Rust v1.76.0 或最新稳定版](https://www.rust-lang.org/tools/install)
- [Forc v0.49.3 及最新工具链](https://install.fuel.network/latest)

## 本地运行项目

### 📚 1. 获取仓库

1. 访问 [Fuel Explorer](https://github.com/FuelLabs/fuel-explorer) 仓库并fork该项目。
2. 然后将fork后的副本克隆到本地机器上并开始工作。

```sh
git clone https://github.com/FuelLabs/fuel-explorer
cd fuel-explorer
```

### 📦 2. 安装依赖

```sh
pnpm install
```

### 📒 3. 运行本地节点

此命令将启动基本的开发服务：

- `L1` 本地节点（处理以太坊区块链）；
- `Fuel` 本地节点（处理L2链）；
- `Postgres` 数据库（我们用来索引数据）；

```
pnpm node:start
```

> 你可以在 [docker-compose.yml](https://github.com/FuelLabs/fuel-explorer/blob/main/docker/docker-compose.yml) 文件中查看详情。

### 💻 4. 运行Web应用

现在你已经启动了本地节点，可以开始前端开发了。

1. 在 `packages/app-explorer` 目录下基于提供的示例创建 `.env` 文件

```sh
cp packages/app-explorer/.env.example packages/app-explorer/.env
```

2. 使用以下命令启动前端：

```sh
pnpm dev
``` 

运行该命令后，你可以在浏览器中打开 [http://localhost:3000](http://localhost:3000) 查看 explorer 是否正常运行。

## 🧪 运行E2E测试

1. 使用以下命令安装 `Playwright` 及其依赖项，包括 `Chromium`

```sh
pnpm exec playwright install --with-deps chromium
```

2. 在 `packages/graphql` 目录下基于提供的示例创建 `.env` 文件

```sh
cp packages/graphql/.env.example packages/graphql/.env
```

3. 启动本地节点服务器

```sh
pnpm node:start
```

4. 最后，可以使用以下命令运行E2E测试：

```sh
pnpm test:e2e
```

## 🧰 有用的脚本

为了让开发更方便，我们在 [package.json](https://github.com/FuelLabs/fuel-explorer/blob/main/package.json) 中添加了许多有用的脚本。
以下是开发过程中最常用的一些脚本：

```sh
pnpm <command name>
```

| 脚本             | 描述                                                |
| -------------- | ------------------------------------------------- |
| `dev`          | 运行开发服务器（仅前端）                             |
| `node:start`   | 使用 `fuel-core` 和 `faucet` API 运行本地网络。      |
| `node:stop`    | 停止所有容器但不删除数据                             |
| `node:clean`   | 停止并删除本地运行的所有开发容器                      |
| `node:restart` | 重启所有容器但不删除数据                             |
| `test:e2e`     | 运行E2E测试                                         |
| `ts:check`     | 运行TypeScript编译器                                 |

> 其他脚本可以在 [package.json](https://github.com/FuelLabs/fuel-explorer/blob/main/package.json) 中找到。

---

# 参考资料

[FuelLabs/fuel-explorer](https://github.com/FuelLabs/fuel-explorer)