# Deploying & Debugging the Smart Contracts on Polygon
![Deploying   Debugging the Smart Contracts on Polygon by Akhilesh Thite](https://user-images.githubusercontent.com/68826419/128823287-bb88b2f1-5505-4f0a-aa0c-d67708d58546.png)
In this article, I'll show you how to deploy smart contracts of your DApp to the Polygon (Matic) Mumbai Test Network.
I'll cover all the possible errors which I faced during the deployment.
So, grab a cup of coffee ☕️ and follow the steps.

## 1. MetaMask setup.
To deploy the smart contracts on Matic you first have to create a Matic network in MetaMask wallet.
`Settings -> Networks -> Add network -> Save`<br>
<img style="align:center" href="https://user-images.githubusercontent.com/68826419/128823596-49410c34-9244-42a2-ac3e-1ee3beff63f6.png"></img><br>
To get test Matic for deployment and testing, 
go to -> [Matic Faucet](https://faucet.matic.network) -> Select Mumbai -> Paste wallet address -> Submit
Done! check your wallet, you'll see some Matic there.

## 2. truffle-config
`truffle-config.js` for Mac users
`truffle.js` for Windows users
truffle-config file is the main and the most important file of your DApp which interacts with everything. In this file, you can mention the path of your solidity file (smart contracts), ABI's, and define networks.
```javascript
const HDWalletProvider = require("@truffle/hdwallet-provider")
require('dotenv').config(); //for MNEMONIC

module.exports = {
  networks: {
   // For Ganache, your personal blockchain
   development: {
      host: "127.0.0.1",     // Localhost (default: none)
      port: 8545,            // Standard Ethereum port 
      network_id: "*",       // Any network (default: none)
    },
    matic: {
      provider: () => new HDWalletProvider(process.env.MNEMONIC, 
     `https://rpc-mumbai.maticvigil.com/v1/process.env.PROJECT_ID`),
      network_id: 80001,
      confirmations: 2,
      timeoutBlocks: 200,
      skipDryRun: true,
    },
  },
  contracts_directory: './src/contracts/',
  contracts_build_directory: './src/abis/',
  compilers: {
    solc: {
      optimizer: {
        enabled: true,
        runs: 200
      }
    }
  }
}
```
