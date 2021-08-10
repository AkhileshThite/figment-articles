# Build a Social Media DApp & Deploy it on Polygon
![Build a Social Media DApp   Deploy it on Polygon by Akhilesh Thite](https://user-images.githubusercontent.com/68826419/128836864-2f40f55f-66fd-4f79-822f-883ad1d03106.png)
<br>
In this tutorial, I'll show you how to Build a Social Media DApp just like YouTube & how to Deploy it on Polygon (Matic) Mumbai Test Network.<br>
I'll start the tutorial from scratch (MetaMask installation process to hosting the DApp on IPFS using Fleek).<br>
So, grab a cup of coffee ☕️ and let's get started!

## About the Author
I'm Akhilesh Thite, an Indian tech enthusiast with a passion for Software Development, Open-Source, Decentralization & AI. Feel free to contact me on [GitHub](https://github.com/AkhileshThite) & [Twitter](https://twitter.com/AkhileshThite_).

## Basics & Installation Setup
We need the following things on your computer to build our DApp.
### Node & npm:
<img height="150" width="150" align="left" src="https://user-images.githubusercontent.com/68826419/128867676-c789b537-9881-49cc-a044-32b672f99680.png" /> Node is a JavaScript runtime environment that executes JavaScript code outside a web browser and npm is a JavaScript package installer.
<br>
To install Node.js & npm on your computer, click on this [link](https://nodejs.org/en/download/) -> download the file as per your computer requirement -> Install the file.
<br>
To check the successful installation type `npm -v` in cmd prompt or terminal, It'll show the version that means you've successfully installed it on your computer.
<br>

### Truffle:
<img height="150" width="150" align="left" src="https://user-images.githubusercontent.com/68826419/128867776-82b05234-7301-443a-9784-388ba7e3638e.png" />Truffle is the best development environment for developing blockchain applications. Truffle gives us boilerplate code (template code) to start building our DApp.<br>
To install truffle open your `windows cmd prompt` or `mac terminal` and paste the following command.
<br>
`npm install -g truffle`
<br>

### Ganache (Optional for this tutorial):
<img height="150" width="150" align="left" src="https://user-images.githubusercontent.com/68826419/128867841-498dc62c-a8fd-47ee-818d-4cc6c9cc2382.png" />Ganache is a personal blockchain environment for DApp development. It provides us 10 ETH accounts, each of them is funded with 100 ETH so you don't have to worry about anything. 
<br>
But in this tutorial, we will deploy our smart contracts on Polygon (Matic).
<br>
If you're looking to develop your own DApp then Ganache is the powerful tool. You can download Ganache from this [link](https://www.trufflesuite.com/ganache)
<br>

### MetaMask Setup
<img height="150" width="150" align="left" src="https://user-images.githubusercontent.com/68826419/128867893-60b76424-ba7b-4d12-bf0a-e42aacb46fca.png" />MetaMask is used to interact with the Ethereum blockchain. It allows users to access their Ethereum wallet through a browser extension or mobile app, which can then be used to interact with decentralized applications.
<br>
To install MetaMask extension, head over to `Google Chrome extension store -> search for the word "MetaMask" -> install the extension`
<br>
Now, `Create a MetaMask account -> save the mnemonics (12 secret words) because we need those mnemonics at the time of deployment`
<br>
To deploy the smart contracts on Matic we first have to create a Matic network in MetaMask wallet. `Settings -> Networks -> Add network -> Save`
<br>
Create a Matic network. Fill out the information as given in the image below.
<br>
<div align="center"><img src="https://user-images.githubusercontent.com/68826419/128823596-49410c34-9244-42a2-ac3e-1ee3beff63f6.png" /></div>
<br>
Now you'll notice zero balance (0 MATIC) in your wallet, To get test Matic for deployment and testing,<br>
go to Matic Faucet -> Select Mumbai -> Paste wallet address -> Submit<br>
Matic Faucet link: https://faucet.matic.network <br>
Done! check your wallet, you'll see some Matic there. 5 Matic are enough for deployment and testing the DApp.
<br>
<div align="center"><img src="https://user-images.githubusercontent.com/68826419/128877273-327f6d3d-24a2-4637-8392-004a1f62048a.png" /></div>
