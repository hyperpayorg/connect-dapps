# Introduction
This doc will show how to connect the Dapps in HyperPay wallet.

# DApp Development
## How To Show HyperPay Wallet
  If DAPP wants to show HyperPay wallet info in DAppBrowser. There are several ways to do.
  1. If DAPP uses [web3-onboard](https://github.com/blocknative/web3-onboard) to integrate the wallet, nothing needs to be done. Hyperpay DappBrowser can directly display relevant wallet information, as shown in the following picture:
  ![Web3 Onborad Demo](assets/16547625247238.jpg)
 web3-onboard supports wallets:
  ```js
  export enum ProviderLabel {
  AlphaWallet = 'AlphaWallet',
  AToken = 'AToken',
  Binance = 'Binance Smart Wallet',
  Bitpie = 'Bitpie',
  BlockWallet = 'BlockWallet',
  Brave = 'Brave Wallet',
  Coinbase = 'Coinbase Wallet',
  Dcent = `D'CENT`,
  Detected = 'Detected Wallet',
  Frame = 'Frame',
  HuobiWallet = 'Huobi Wallet',
  HyperPay = 'HyperPay',
  ImToken = 'imToken',
  Liquality = 'Liquality',
  MeetOne = 'MeetOne',
  MetaMask = 'MetaMask',
  MyKey = 'MyKey',
  Opera = 'Opera Wallet',
  OwnBit = 'OwnBit',
  Status = 'Status Wallet',
  Trust = 'Trust Wallet',
  TokenPocket = 'TokenPocket',
  TP = 'TP Wallet',
  WalletIo = 'Wallet.io',
  XDEFI = 'XDEFI Wallet',
  OneInch = '1inch Wallet',
  Tokenary = 'Tokenary Wallet',
  Tally = 'Tally Wallet'
}
```
  
  2.  If DAPP wants to display HyperPay  directly. We can provide wallet logo, etc.   
## How To Connect Wallet 
### EVM(Ethereum) Connect
The Metamask protocol is a universal wallet connection scheme for Ethereum or EVM chains. HyperPay complies with the Metamask protocol by default, and will implant window.ethereum object in the webview. Developers can directly develop follow [MetaMask Documents](https://docs.metamask.io/guide/ethereum-provider.html).

```js
(function() {
    var config = {
        address: "\(address.lowercased())",
        chainId: \(chainId),
        rpcUrl: "\(rpcUrl)"
    };

    window.ethereum = new hiWallet.Provider(config);
    window.web3 = new hiWallet.Web3(window.ethereum);
    window.isHyperPay = true;
    
})();
```
# DappBrowser Methods Supports

```swift
enum DAppMethod: String, Decodable, CaseIterable {
    case signTransaction
    case signPersonalMessage
    case signMessage
    case signTypedMessage
    case ecRecover
    case requestAccounts
    case watchAsset
    case addEthereumChain
    case switchEthereumChain
}
```
# Resources

[website](https://www.hyperpay.tech/)
[logo image]()
etc.