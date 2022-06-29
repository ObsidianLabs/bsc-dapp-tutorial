# BNB 快速开发指南

简体中文 | [English](https://github.com/ObsidianLabs/bsc-dapp-tutorial/blob/master/README.EN.md)

## 目录 
- [关于BNB链](#关于BNB链)
- [准备BNB数字钱包](#准备BNB数字钱包)
    + [使用浏览器插件钱包](#使用浏览器插件钱包)
    + [使用APP钱包](#使用APP钱包)
- [准备BNB的开发环境](#准备BNB的开发环境)
    + [使用BNB Studio开始一站式开发旅程](#使用BNBStudio开始一站式开发旅程)
    + [通过网页端在线体验 BNB 合约开发](#通过网页端在线体验BNB合约开发)
- [接入BNB网络](#接入BNB网络)
- [BNB 智能合约开发](#BNB智能合约开发)   
    + [BNB开发中的关键工具](#BNB开发中的关键工具)
    + [创建智能合约项目](#创建智能合约项目)
    + [合约部署和调用](#合约部署和调用)
- [开发完整的BNB dApp应用](#开发完整的BNB-dApp应用)

## 关于BNB链
BNB 链（BNB Chain）是一条以太坊虚拟机兼容，包括币安链与币安智能链的区块链系统。BNB 是加密资产行业顶尖项目的测试和前沿探索。通过引入权益权威证明（PoSA）共识机制，BNB 创建了验证一个允许节点、代币持有者、开发者和用户都能够从区块链中获益的生态系统，享受更高的性能和更充裕的创新空间。


官方网站：https://www.binance.org/cn/smartChain

本文为 BNB 开发快速上手指南，希望为开发者提供指导和帮助。

## 准备BNB数字钱包
在区块链应用中，数字钱包装载的并不是数字货币，而是密钥（私钥和公钥）。数字钱包中包含成对的私钥和公钥，公钥用于交易转账，私钥用于签名和解密。拥有了密钥相当于拥有相应地址上数字货币的支配权。在开发流程中，我们通过钱包来创建随机私钥、公钥、以及一串用于交易的地址信息。这段地址信息可以用于接受他人转账的数字货币，以及把你所拥有的数字货币转账给其他人。因此在我们开发智能合约之前，首先要先准备一个数字钱包。
对于币安智能链来说，我们推荐使用浏览器插件钱包或者APP钱包作为管理密钥的工具。

### 使用浏览器插件钱包
在开发过程当中，最常用的是浏览器插件钱包。浏览器插件钱包配置简单，插件钱包的安装和使用都很便捷。此外，由于目前大多数区块链应用都是网页的，因此通过浏览器钱包可以轻松访问目前主流的所有 Defi 和 NFT 应用。

|  |  钱包  |  地址  |  教程  |
|:---:|:---:|---|---|
|  1  |  MetaMask  |  https://metamask.io/  | https://docs.binance.org/smart-chain/wallet/metamask.html  |
|  2  |  Binance Chain Wallet | https://chrome.google.com/webstore/detail/binance-chain-wallet/fhbohimaelbohpjbbldcngcnapndodjp?hl=en  | https://binance-wallet.gitbook.io/binance-chain-extension-wallet/

需要大家注意的是，Binance Chain Wallet  同时支持币安链 (Binance Chain) 和 币安智能链 (BNB Chain)，这是两条不同的链，需要大家注意区分。
### 使用 APP 钱包 
在智能合约上线以后，大部分用户会选择使用APP钱包来访问并使用。

|   |	钱包 |	地址 | 教程 |
|:---:|:---:|---|---|
| 1 |	TrustWallet |	https://trustwallet.com/  | https://www.binancezh.cc/zh-CN/blog/421499824684901157  |
| 2	| 麦子钱包(MathWallet) |	https://www.mathwallet.org/zh-cn/ | https://blog.mathwallet.xyz/?p=3895  |
| 3 |	TokenPocket	| https://www.tokenpocket.pro/zh/ | https://mp.weixin.qq.com/s/xXjP_qAOF31f-mGauXl7Kw |


## 准备BNB的开发环境
### 使用BNB Studio开始一站式开发旅程
BNB Studio 是一套功能强大且简便易用的BNB币安智能链图形化IDE开发平台。它支持运行于包括Windows, macOS以及Linux等主流操作系统在内的桌面端，也可以运行于Web端。相较于以Remix和Ganache为代表的传统的以太坊开发工具链，BNB Studio优化了BNB开发环境的检测和安装，并整合了完整开发流程中必需的工具，例如图形化代码编辑器，项目管理器，密钥管理器，区块浏览器，合约调试器以及网络链接管理器。
通过桌面端进行本地开发

桌面端包含完整的开发工具，适合从新手到资深团队等不同阶段的 BNB 开发者。用户可以前往[Github Repo](https://github.com/ObsidianLabs/BNB-Studio) 下载最新版的BNB Studio桌面端软件，目前支持包括macOS，Linux和Windows在内的主流操作系统。
安装
* macOS: 双击打开 `BNB-Studio-x.x.x.dmg` 并将 BNB Studio 拖动到应用文件夹内
* Linux: 双击打开 `BNB-Studio-x.x.x.AppImage`, *选择 Properties( => Permissions => Execute, 将 Allow executing file as progrom 选项打勾。关闭属性设置窗口并双击打开应用（不同的 Linux 发行版可能会有不同的安装方式*
* Windows: 双击打开 `BNB-Studio-x.x.x.exe`。
准备环境依赖
在正确安装 BNB Studio 并初次启动时，你将看到一个欢迎页面，这里有正常运行币安智能链 BNB 开发所需要的依赖，包括了 Docker，BNB Node 以及Truffle.
* BNB Studio 使用[Docker](https://www.docker.com/) 来启动 BNB 节点和进行项目编译。如果你之前没有安装过 Docker，可以点击 *Install Docker* 按钮访问 Docker 官方网站并进行下载安装；
* [BNB Docker Hub](https://hub.docker.com/repository/docker/obsidians/bsc)存储着BNB 节点镜像，BNB Studio 使用这个镜像来运行 BNB 节点；
* [BNB Truffle](https://hub.docker.com/repository/docker/obsidians/truffle) BNB Studio 使用Truffle工具包进行项目的创建和编译。

当所有依赖都正确安装并运行后，灰色的 Skip 按钮将会变成绿色的 Get Started  按钮。点击这个按钮进入主界面，就可以开始智能合约开发了！

<p align="center">
  <img src="./screenshots/startup.jpg" width="800px">
</p>

### 通过网页端在线体验 BNB 合约开发 
BNB Studio提供了Web版供大家在线编译和运行 BNB 合约。Web版本在集成了BNB Studio桌面版本绝大多数功能的同时，省略了开发者在本地准备和调试开发环境的过程，降低了开发者的入门的门槛，适合刚刚加入 BNB 生态的轻度开发者使用。开发用户可以前往 [bsc.ide.black](http://bsc.ide.black/) 立刻刻开始云端开发新体验。


<p align="center">
  <img src="./screenshots/main.jpg" width="800px">
</p>


关于 BNB Studio 的更多使用说明，请参见 [Github Page](https://github.com/ObsidianLabs/BSC-Studio)


## 接入BNB网络
BNB 主要有两个网络，分别为主网 (BNB Mainnet) 和测试网 (BNB Testnet)。：
* BNB测试网，是供开发者进行合约测试使用的，测试网上的token是可以免费领取 (通过Faucet)，测试网Token没有任何经济价值。
* BNB主网，是智能合约正式部署的网络，用户实际是在主网上使用你的智能合约，主网上的代币（BNB及BEP20标准）是有实际经济价值的。

BNB Studio 已经在软件中预配置了BNB主网和测试网的链接，可以方便的进行切换。为了方便用户在网络上进行开发，我们集成了很多工具，涵盖了浏览器钱包（密钥管理，转账工具) 、BNB 区块浏览器、Faucet等日常需要的工具。

BNB区块浏览器
如果需要查询网络信息和链上数据，BNB提供了测试网区块浏览器[testnet.bscscan.com](https://testnet.bscscan.com/) 主网区块浏览器[bscscan.com](https://bscscan.com/)供开发者和用户查询链上数据。

Faucet
在使用BNB测试网开发中，我们需要使用 token 进行合约的部署、调用、转账等操作。通过测试网的 [Faucet](https://testnet.binance.org/faucet-smart) 服务，可以申请测试Token。同样的，BNB Studio 集成了Faucet按钮 [Faucet功能](https://github.com/ObsidianLabs/BSC-Studio#faucet)，方便用户使用 Faucet 服务获取测试代币。








## BNB 智能合约开发

### BNB开发中的关键工具

[Truffle](https://www.trufflesuite.com/truffle)
Truffle是一套基于Solidity语言的开发框架，它简化了去中心化应用（Dapp）的构建和管理流程。Truffle本身是采用Javascript编写，支持智能合约的编译、部署和测试。
Truffle开发框架提供了很多功能，简化了我们的开发、编译、部署与调试过程合约开发编辑部署调用。

[Solc](https://github.com/ethereum/solidity)
solc是Solidity的命令行编译器，Solidity编写的以太坊智能合约可通过带参数的命令行工具solc进行编译，成为以太坊虚拟机中的代码。最终部署到链上形成我们所见到的各种智能合约。

[BNB Client (base on Geth)](https://github.com/binance-chain/bsc)
基于以太坊黄皮书，任何人都能够以他们认为合适的语言创建自己的以太坊节点实现。
迄今为止最受欢迎的客户是Geth和Parity。实现的不同之处主要在于选择的编程语言：Geth使用Golang，而Parity使用Rust。而Geth是目前最受欢迎的客户端实现。
BNB Client是基于Geth开发的BNB节点应用，BNB主网和BNB测试网节点都是通过这个应用来运行的。在本地开发中，我们可以自己安装BNB Client，在本地机器上运行自己的BNB节点和BNB本地开发网络。

BNB Studio 已经集成了包括Truffle, Solc 和 BNB Client在内的所有关键开发工具。

### 创建智能合约项目
BNB Studio中集成了若干智能合约模版，你可以选择对应的模版，创建第一个智能合约项目，并开始智能合约开发。这些模版包括：
* Coin:一个非常基本的代币合约）
* [Open Zeppelin](https://openzeppelin.com/):基于Open Zeppelin模版，提供了ERC-20，ERC-721（NFT）等合约。
* [MetaCoin](https://github.com/truffle-box/metacoin-box):基于Truffle的MetaCoin模版.
 
<p align="center">
  <img src="./screenshots/project.png" width="800px">
</p>

### 合约部署和调用

使用 BNB Studio 可以快速进行：
1. [合约部署](https://github.com/ObsidianLabs/BSC-Studio#部署智能合约项目)
2. [合约调用](https://github.com/ObsidianLabs/BSC-Studio#调用合约)

点击链接可以查看相关教程。



## 开发完整的BNB dApp应用

我们刚刚编写部署的智能合约是一个在BNB链上运行的服务，它规定一系列链上的交易以完成我们开发中所设定好的功能任务。它相当于传统互联网开发中的后台服务。为了使用户能够方便的调用这些底层服务，避免不必要的门槛和编程的麻烦，我们也还需要编写一个前端应用作为用户界面，这个前端应用以及我们编写的后端智能合约合体就成为了一个简单易用的区块链应用，也叫去中心化应用或者dApp。

成功开发一个Dapp 的关键需要以下几步：
* 集成前端SDK：可以使用任何以太坊支持的SDK，例如web3.js或者ethers.js
* 使用BNB的rpc接口配置SDK：BNB提供的rpc接口可以在这里查看[BNB-RPC](https://docs.binance.org/smart-chain/developer/rpc.html)
* 集成浏览器插件对应的SDK：例如MetaMask或Binance Wallet Wallet
* 如果希望查询一些rpc接口不支持的链上数据（例如交易记录，token信息），还可以集成区块链浏览器的接口[BNB Scan APIs](https://bscscan.com/apis)

我们提供了一个完成上述集成的[BNB dApp 示例](https://github.com/ObsidianLabs/bsc-dapp-example)

在这个例子中：
* 应用在启动的时候会自动检测浏览器插件钱包，包括 Metamask 和 Binance Chain Wallet；
* dApp也将会自动检测目前正在连接的网络（BNB主网或BNB测试网）；
* 检测成功后，插件会弹出窗口请求用户授权访问；
* 完成授权后 dApp 便可以访问到对应地址的信息，如地址和余额信息；
* dApp 提供转账按钮，填入对应信息后点击调用按钮，dApp 会调用浏览器插件弹窗，用户通过插件进行签名后就可以完成交易了；
* dApp同时提供了调用合约的方式。

