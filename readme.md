<h1><center>
    Fuel Network 中文开发者教程
</center> </h1>

欢迎来到Fuel Network中文开发者教程！

本教程将指导您如何在Fuel Network上进行开发，帮助您快速上手并掌握核心概念。



## 目录


1. [简介](#简介)
2. [环境配置](#环境配置)
3. [创建第一个项目](#创建第一个项目)
4. [编写智能合约](#编写智能合约)
5. [部署与测试](#部署与测试)
6. [高级主题](#高级主题)
7. [常见问题](#常见问题)
8. [参考资料](#参考资料)

## 正文

### 简介
Fuel 是一个基于 UTXO 的模块化执行层，为以太坊带来了全球可访问的规模。作为模块化执行层，Fuel 可以以单片链无法实现的方式实现全局吞吐量，同时继承以太坊的安全性。

## 环境配置

在开始开发之前，您需要进行一些环境配置：

1. 安装 Rust 编译器：

    ```sh
    curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
    source $HOME/.cargo/env
    ```

3. 安装 Fuel Network 开发工具：
    ```sh
    cargo install forc
    ```

4. 克隆 Fuel Network 仓库：
    ```sh
    git clone https://github.com/FuelLabs/fuel-core
    cd fuel-core
    ```

## 创建第一个项目

创建一个新的Fuel项目：

```sh
forc new my-first-fuel-project
cd my-first-fuel-project
```

这将创建一个新的Fuel项目目录，其中包含基本的项目结构和示例代码。

## 编写智能合约

在 `src/main.sw` 文件中编写您的第一个智能合约：

```rust
contract;

abi MyContract {
    fn greet(name: str[20]) -> str[20];
}

impl MyContract for Contract {
    fn greet(name: str[20]) -> str[20] {
        return str[20]::from("Hello, ") + name;
    }
}
```

## 部署与测试

构建并部署您的智能合约：

```sh
forc build
forc deploy --url http://node-url
```

运行测试以确保您的合约工作正常：

```sh
forc test
```

## 高级主题

1. **优化智能合约性能**：
    - 使用内联汇编提高执行效率。
    - 利用Fuel Network特有的存储优化技术。

2. **与前端集成**：
    - 使用Fuel SDK与前端应用进行交互。
    - 构建用户友好的界面与Fuel合约互动。

## 常见问题

- **如何调试合约？**
    - 使用 `forc debug` 命令运行调试器。
  
- **如何管理合约版本？**
    - 使用 `forc update` 命令更新依赖项和合约版本。

## 参考资料

- [Rust 编程语言](https://www.rust-lang.org/zh-CN/)
- [Fuel Network 官方文档中文翻译](https://docs.fueldev.xyz)
- [Fuel Network GitHub 仓库](https://github.com/FuelLabs)

感谢您的阅读！希望本教程能帮助您在Fuel Network上快速上手并进行开发。如果您有任何问题或建议，请提交 issue 或 pull request。



## 贡献者
[![contrib graph](https://contrib.rocks/image?repo=fuel-champions/Fuel-Dev-tutorial-CN)](https://github.com/fuel-champions/Fuel-Dev-tutorial-CN/graphs/contributors)  

贡献者是项目持续构建的原动力。


## 关于我们
[FuelDevCN](https://github.com/FuelDevCN)是自主发起的Fuel中文开发者社区，持续构建和更新Fuel及Swag语言相关中文信息、资讯、教程及其研报。

### X/Twitter
[![Twitter](https://img.shields.io/badge/@fueldevcn-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/fueldevcn)


### 微信群
请加 `YanboAtWeb3` 备注 Fuel


### 邮件
[![Mail](https://img.shields.io/badge/fueldevcn@gmail.com-0078D4?style=for-the-badge&logo=microsoft-outlook&logoColor=white)](mailto:fueldevcn@gmail.com
)


