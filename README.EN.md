# BSC Development Quick Reference Guide

English | [简体中文](https://github.com/ObsidianLabs/bsc-dapp-tutorial#readme)

## Catalog
- [About Binance Smart Chain](#About-Binance-Smart-Chain)
- [Get Your BSC Wallet Ready](#Get-Your-BSC-Wallet-Ready)
    + [Using Browser Plugin Wallet](#Browser-Plugin-Wallet)
    + [Using Wallet App](#Wallet-App)
- [Preparing BSC Development Environment](#Preparing-BSC-Development-Environment)
    + [Develop locally with BSC Studio Desktop](#Develop-locally-with-BSC-Studio-Desktop)
    + [Develop online with BSC Studio Web](#Develop-online-with-BSC-Studio-Web)
- [Connecting to BSC networks](#Connecting-to-BSC-networks)
- [BSC Smart Contract Development](#BSC-Smart-Contract-Development)   
    + [Key Tools in BSC Development](#Key-Tools-in-BSC-Development)
    + [Creating Smart Contract Project](#Creating-Smart-Contract-Project)
    + [Contract Deployment and Interaction](#Contract-Deployment-and-Interaction)
- [Developing a complete Dapp](#Developing-a-complete-Dapp)

## About Binance Smart Chain
Binance Smart Chain (BSC) is a sovereign smart contract blockchain delivering Ethereum Virtual Machine (EVM) compatible programmability and running parallel with Binance Chain. By introducing the Proof of Stake Authority (PoSA) consensus mechanism, BSC has created an ecosystem that allows nodes, token holders, developers, and users to benefit from the blockchain. 

This article is a quick start guide for BSC developers, hoping to provide developers with help.

## Get Your BSC Wallet Ready
In the blockchain world, digital wallet is not the actual container for cryptocurrencies. Rather, it stores pairs of encryption keys that represents ownership at certain address. Each pair of keys stored in digital wallets consists of a public key that is needed to initiate transactions and a matching private key for transaction encryptions and decryptions. Therefore, ownership of keypairs confers full control of the cryptocurrencies at the address associated to the keypairs. In development stage, we create randomized keypairs and a piece of address information through our digital wallet, with which we are able to receive from or send to cryptocurriencies to others. And this is why we have to get our wallet ready for development. 

We highly recommend to use **Browser Plugin Wallet** or **Wallet App** to manage keypairs while developing on Binance Smart Chain.

### Browser Plugin Wallet
Browser plugin wallet is the most popular choice in blockchain development. It's easy to set up, install and access the wallet in the browser. Besides that, since majority of blockchain applications are web-based, browser plugin wallet gives a intuitive access to pretty much all DeFi and NFT apps available on the market.

|  |  Wallet  |  Address  |  Tutorial  |
|:---:|:---:|---|---|
|  1  |  MetaMask  |  https://metamask.io/  | https://docs.binance.org/smart-chain/wallet/metamask.html  |
|  2  |  Binance Chain Wallet | https://chrome.google.com/webstore/detail/binance-chain-wallet/fhbohimaelbohpjbbldcngcnapndodjp?hl=en  | https://binance-wallet.gitbook.io/binance-chain-extension-wallet/

*Please note*，**Binance Chain Wallet**  supports both **Binance Chain** and ***Binance Smart Chain(BSC)** and they're two distinctive blockchains that sometimes confuses people.

### Wallet App 
When a smart contract goes live, most of its users access it through a wallet app of their choice.

|   |	Wallet |	Address | Tutorial |
|:---:|:---:|---|---|
| 1 |	TrustWallet |	https://trustwallet.com/  | https://www.binancezh.cc/zh-CN/blog/421499824684901157  |
| 2	| MathWallet |	https://www.mathwallet.org/zh-cn/ | https://blog.mathwallet.xyz/?p=3895  |
| 3 |	TokenPocket	| https://www.tokenpocket.pro/zh/ | https://mp.weixin.qq.com/s/xXjP_qAOF31f-mGauXl7Kw |


## Preparing BSC Development Environment
### Start Development today with BSC Studio
BSC Studio is a powerful yet user-friendly graphic IDE platform, specially designed for BSC. It supports running locally on majority OS, including macOS, Windows and Linux and also on web browsers. Comparing with traditional Ethereum development toolkit like Remix and Ganache, BSC Studio streamlines enviroment preparation procedure and integrates essential tools for a complete development lifecycle, including a graphic code editor, project manager, keypair manager, block explorer, contract inspector and network manager. 

### Develop locally with BSC Studio Desktop
BSC Studio Desktop is a great all-in-one IDE platform for BSC developers at all levels. You may download the latest release of BSC Studio Desktop at its [Github Repo](https://github.com/ObsidianLabs/BSC-Studio) . BSC Studio currently supports major OS including macOS, Linux and Windows.

#### Installation
* macOS: Double click to open *BSC-Studio-x.x.x.dmg* and drag the app into Application folder.
* Linux: Double click to open *BSC-Studio-x.x.x.AppImage*, Select *Properties( => Permissions => Execute* and tick *Allow executing file as progrom* option. Close Properties window and double click to open the application.**Please note, different Linux distribution might have different application installation procedure.**
* Windows: Double click to open *BSC-Studio-x.x.x.exe*

#### Preparing Prerequisites 
Upon first successful startup of BSC Studio, you'll be directed to a welcome screen where shows a list of prerequisites for BSC Development, including Docker, BSC Node and Truffle.
* BSC Studio relies on [Docker](https://www.docker.com/) to start BSC node and compile projects. If you haven't had Docker on your machines yet, click on *Install Docker* to visit official Docker website to download latest release and install.
* [BSC Docker Hub](https://hub.docker.com/repository/docker/obsidians/bsc) stores Docker images for BSC nodes, which BSC Studio relies on to run BSC node.
* [BSC Truffle](https://hub.docker.com/repository/docker/obsidians/truffle) is the truffle toolkit used by BSC Studio for project creation and compilation.

When all prerequisites are succesfully installed and started on local machine, a green *Get Started* button will replace the gray *Skip* button. Now go ahead and click to start your smart contract development!

<p align="center">
  <img src="./screenshots/startup.jpg" width="800px">
</p>

### Develop online with BSC Studio Web
BSC Studio also offers a web version for developers who wish to develop, compile and run BSC smart contracts online. BSC Studio web inherits most functionalities of the Desktop version but no longer require setting up dependencies on local machines. It's the perfect choice for BSC developers who wants to try out BSC development without worrying about setting up BSC dependencies locally. Visit [bsc.ide.black](http://bsc.ide.black/) to experience BSC decelopment on the cloud.

<p align="center">
  <img src="./screenshots/main.jpg" width="800px">
</p>


For more information and tutorials on BSC Studio, check out BSC Studio [Github Page](https://github.com/ObsidianLabs/BSC-Studio)


## Connecting to BSC networks
BSC primarily offers two networks, namely BSC Mainnet and BSC Testnet.
* BSC Testnet, is a test network for test purposes, where testnet tokens can be *faucet* free of charge and therefore contains no monetary value. 
* BSC Mainnet, is the main network for production applications. Users are interacting with smart contracts on the mainnet and thus Mainnet tokens (BNB/BEP20) are actual cryptocurrencies. 

BSC Studio has BSC mainnet and testnet connection preconfigured in the application and you may easily switch between these two networks. In order to support smoother development on BSC networks, BSC Studio comes with a set of built-in tools like Browser Wallet, Block Explorer, Faucet Tool, covering the most popular tools among BSC developers.

### BSC Block Explorer
BSC offers block explorer apps for network and on-chain information inquiry, Click to access [Testnet Explorer - testnet.bscscan.com](https://testnet.bscscan.com/) or [Mainnet Explorer - bscscan.com](https://bscscan.com/).

### BSC Data Solution
If you're no longer satisfied with the chain's speed in sync as a result of scalability limited by native nodes, StreamingFast offers an alternative streaming solution with full history for those who wants to get real-time updates of contracts, account balances, AMM prices or sync their local database, with speed 50x faster than nodes. Available to everyone for free at [StreamingFast.io]https://streamingfast.io

### Faucet
Developers often needs tokens when developing on BSC Testnet to play with contract or to make transactions. BSC Testnet offers [Faucet](https://testnet.binance.org/faucet-smart) service to acquire free testnet tokens， of course BSC Studio also integrates [Faucet Functionality](https://github.com/ObsidianLabs/BSC-Studio#faucet) in the toolbar for easier invocation to faucet tokens.

## BSC Smart Contract Development

### Key Tools in BSC Development

[Truffle](https://www.trufflesuite.com/truffle)
Truffle is a development framework based on Solidity that aim to simplifies construction and management process of Dapp. Truffle is written in Javascript comes with a powerful set of features to support compilation, deployment and test of smart contracts. 

[Solc](https://github.com/ethereum/solidity)
solc is command line compiler for Solidity. It compiles smart contract code written in Solidity into binary code in EVM and eventually deploy to act just like other smart contracts we have seen on chain.

[BSC Client (base on Geth)](https://github.com/binance-chain/bsc)
Based on Ethereum Yellow Paper, anyone are allowed to construct their Ethereum node with a programming language of their choice, however the most popular clients so far go to **Geth** and **Parity**. The difference is mainly the language, where Geth is written in Golang while Parity is made of Rust. Amond these two, Geth is more popular and thus is the client implementation we use here.
BSC Client is a BSC client application based on Geth, where both our BSC nodes (Testnet/Mainnet) are running on it. We can also run our own BSC nodes and local development network with self-installed BSC client of our choice.

**BSC Studio** has intergrated all essentials development tools including Truffle, solc and BSC Client.

### Creating Smart Contract Project
BSC Studio integrates a few smart contract template. You may create your first smart contract project with a corresponding template and start building your smart contract instantly. Built-in templates include:
* Coin: A basic token-based smart contract
* [Open Zeppelin](https://openzeppelin.com/): A smart contract offers ERC-20, ETC-721(NFT) tokens, based on Open Zeppelin.
* [MetaCoin](https://github.com/truffle-box/metacoin-box):A MetaCoin template based on Truffle.
<p align="center">
  <img src="./screenshots/project.png" width="800px">
</p>

### Contract Deployment and Interaction

BSC Studio offers one-click automated process to
1. [Contract Deployment](https://github.com/ObsidianLabs/BSC-Studio#Deploy-Smart-Contract-Project)
2. [Contract Interaction](https://github.com/ObsidianLabs/BSC-Studio#Call-the-Contract)

Click to view corresponding tutorials on our Github.

## Developing a complete Dapp

The smart contract we just written is a services running on Binance Smart Chain, it defines a series of on-chain transaction serving the purpose we have set in development. It functions like the backend service in the traditional software practice, so in order to take off the burden of programming, we also need to develop a frontend application to serve as the user interface to the smart contract so that the combination makes a simple, but complete blockchain application, also known as decentralized application or Dapp.

A successful Dapp project requires all of the following steps:
* Integrate front-end SDK: A Ethereum-supported SDK like **web3.js** or **ethers.js**
* Configure SDK with BSC rpc interface: Documentation can be found at [BSC-RPC](https://docs.binance.org/smart-chain/developer/rpc.html)
* Integrate Browser Plugin SDK: such as MetaMask or Binance Chain Wallet
* *Optional* Integrate [BSC Scan APIs](https://bscscan.com/apis) to allow inquiry on-chain data that are not supported by RPC interface (i.e. transaction history, token information)

Here's a complete [BSC dApp Example](https://github.com/ObsidianLabs/bsc-dapp-example) for your reference.

In this example:
* Application auto-detect Browser Plugin Wallet, including **MetaMask** or **Binance Chain Wallet**;
* This dApp auto-detect current network (BSC Testnet/Mainnet);
* If all tests passed, A pop-up windows will show up to request authorization for access;
* This dApp offers **transfer** button. Input required information and press **Execute** button, dApp will invoke pop-up windows through browser plugin where users can sign the transaction to complete it;
* This dApp provides methods to interact with contract.

