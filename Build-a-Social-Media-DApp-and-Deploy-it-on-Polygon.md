# Build a Social Media DApp & Deploy it on Polygon
![Build a Social Media DApp   Deploy it on Polygon by Akhilesh Thite](https://user-images.githubusercontent.com/68826419/128836864-2f40f55f-66fd-4f79-822f-883ad1d03106.png)
<br>
In this tutorial, I'll show you how to Build a Social Media DApp just like YouTube & how to Deploy it on Polygon (Matic) Mumbai Test Network.<br>
I'll start the tutorial from scratch (MetaMask installation process to hosting the DApp on IPFS using Fleek).<br>
So, grab a cup of coffee ☕️ and let's get started!

## Basics & Installation Setup
We need the following things on your computer to build our DApp.
### Node & npm:
Node is a JavaScript runtime environment that executes JavaScript code outside a web browser and npm is a JavaScript package installer.
<br>
To install Node.js & npm on your computer, click on this [link](https://nodejs.org/en/download/) -> download the file as per your computer requirement -> Install the file.
<br>
To check the successful installation type `npm -v` in cmd prompt or terminal, It'll show the version that means you've successfully installed it on your computer.

### Truffle:
Truffle is the best development environment for developing blockchain applications. Truffle gives us boilerplate code (template code) to start building our DApp.<br>
To install truffle open your `windows cmd prompt` or `mac terminal` and paste the following command.
<br>
`npm install -g truffle`

### Ganache (Optional for this tutorial):
Ganache is a personal blockchain environment for DApp development. It provides us 10 ETH accounts, each of them is funded with 100 ETH so you don't have to worry about anything. 
<br>
But in this tutorial, we will deploy our smart contracts on Polygon (Matic).
<br>
If you're looking to develop your own DApp then Ganache is the powerful tool. You can download Ganache from this [link](https://www.trufflesuite.com/ganache)

### MetaMask Setup
MetaMask is used to interact with the Ethereum blockchain. It allows users to access their Ethereum wallet through a browser extension or mobile app, which can then be used to interact with decentralized applications.
<br>
To install MetaMask extension, head over to `Google Chrome extension store -> search for the word "MetaMask" -> install the extension`
<br>
Now, `Create a MetaMask account -> save the mnemonics (12 secret words) because we need those mnemonics at the time of deployment`
<br>
To deploy the smart contracts on Matic we first have to create a Matic network in MetaMask wallet. `Settings -> Networks -> Add network -> Save`
<br>
Create a Matic network. Fill out the information as given in the image below.
<br>
<div align="center"><img src="https://user-images.githubusercontent.com/68826419/128823596-49410c34-9244-42a2-ac3e-1ee3beff63f6.png" /></div><br>



