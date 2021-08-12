# Build a Social Media DApp & Deploy it on Polygon
<div align="center"><img src="https://user-images.githubusercontent.com/68826419/128836864-2f40f55f-66fd-4f79-822f-883ad1d03106.png" /></div>


## Introduction
In this tutorial, I'll show you how to Build a Social Media DApp (Decentralized Apllication) just like YouTube & how to Deploy it on Polygon (Matic) Mumbai Test Network.<br>
I'll start the tutorial from scratch (MetaMask installation process to hosting the DApp on IPFS using Fleek).<br>
So, grab a cup of coffee ☕️ and let's get started!


*About this project: DTube was created by me during the ETHOdyssey Virtual Hackathon in July-Aug 2021. All the resources I used to create this DApp are linked at the bottom in "References" section.*

## Prerequisites
This tutorial assumes that you have some beginner-level experience in programming & blockchain understanding.

## After this tutorial you will be able to:
• Build a Full Stack Decentralized Apllication on top of Ethereum Blockchain.
<br>
• Deploy the smart contracts on polygon (Matic) Mumbai Test Network.
<br>
• Use truffle & MetaMask effectively.
<br>
• Understand Web3 concepts.
<br>
• Host the DApp on IPFS using Fleek platform.

## About the Author
I'm Akhilesh Thite, an Indian tech enthusiast with a passion for Software Development, Open-Source & Decentralization. Feel free to connect with me on [GitHub](https://github.com/AkhileshThite) & [Twitter](https://twitter.com/AkhileshThite_).

## Basics & Installation
We need the following things on your computer to build our DApp.
### Node & npm:
<img height="140" width="140" align="left" src="https://user-images.githubusercontent.com/68826419/128867676-c789b537-9881-49cc-a044-32b672f99680.png" /> Node is a JavaScript runtime environment that executes JavaScript code outside a web browser and npm is a JavaScript package installer.
<br>
To install Node.js & npm on your computer, click on this [link](https://nodejs.org/en/download/) -> download the file as per your computer requirement -> Install the file.
<br>
To check the successful installation type `npm -v` in cmd prompt or terminal, It'll show the version that means you've successfully installed it on your computer.

<br><br>
### Truffle:
<img height="150" width="150" align="left" src="https://user-images.githubusercontent.com/68826419/128867776-82b05234-7301-443a-9784-388ba7e3638e.png" />Truffle is the best development environment for developing blockchain applications. Truffle gives us boilerplate code (template code) to start building our DApp.<br>
To install truffle open your `windows cmd prompt` or `mac terminal` and paste the following command.
<br>
`npm install -g truffle`

<br><br>
### Ganache (Optional for this tutorial):
<img height="150" width="150" align="left" src="https://user-images.githubusercontent.com/68826419/128867841-498dc62c-a8fd-47ee-818d-4cc6c9cc2382.png" />Ganache is a personal blockchain environment for DApp development. It provides us 10 ETH accounts, each of them is funded with 100 ETH so you don't have to worry about anything. 
<br>
But in this tutorial, we will deploy our smart contracts on Polygon (Matic).
<br>
If you're looking to develop your own DApp then Ganache is the powerful tool. You can download Ganache from this [link](https://www.trufflesuite.com/ganache)

<br><br>
### MetaMask Setup:
<img height="150" width="150" align="left" src="https://user-images.githubusercontent.com/68826419/128867893-60b76424-ba7b-4d12-bf0a-e42aacb46fca.png" />MetaMask is used to interact with the Ethereum blockchain. It allows users to access their Ethereum wallet through a browser extension or mobile app, which can then be used to interact with decentralized applications.
<br>
To install MetaMask extension, click on this [link](https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn?hl=en).
<br>
Now, `Create a MetaMask account -> save the mnemonics (12 secret words) because we need those mnemonics at the time of deployment`
<br>
To deploy the smart contracts on Matic we first have to create a Matic network in MetaMask wallet. `Settings -> Networks -> Add network -> Save`
<br>
Create a Matic network. Fill out the information as given in the image below.
<br>
<div align="center"><img src="https://user-images.githubusercontent.com/68826419/128823596-49410c34-9244-42a2-ac3e-1ee3beff63f6.png" /></div>


Now you'll notice zero balance (0 MATIC) in your wallet, To get test Matic for deployment and testing,
<br>
`go to Matic Faucet -> Select Mumbai -> Paste wallet address -> Submit`
<br>
Matic Faucet [link](https://faucet.matic.network)
<br>
Done! check your wallet, you'll see some Matic there. *(We only need small amount of Matic (5-10 Matic) to deploy and test our DApp.)*
<br>
<div align="center"><img src="https://user-images.githubusercontent.com/68826419/128877273-327f6d3d-24a2-4637-8392-004a1f62048a.png" /></div>

### Tech Stack:
**Languages:** `Solidity, JavaScript, HTML5, CSS3`
<br>
**Libraries:** `React.js, Web3.js`
<br>
**Tools:** `IPFS`
<br>
**Network:** `Polygon (Matic)`
<br>
**Platforms:** `Ethereum, Fleek`

### Roadmap:
First, we'll setup our coding environment with the help of **Truffle**, after that we'll write **Smart Contracts** in **solidity**. 
After writing Smart Contracts, To build the front-end of our DApp we'll use **React.js** Javascript library plus some **HTML5, CSS3 & JavaScript**.
<br>
We're going to use **IPFS** (InterPlanetary File System) to store the hashes of our videos to the blockchain and later we'll be able to play those videos by calling those video hashes.
<br>
To connect our Smart Contracts with fron-end we'll use **Web3.js** and then we'll deploy our Smart Contracts on **Polygon (Matic) Mumbai Test Network**. In the final step, we'll host this DApp on IPFS by using the **Fleek** platform.


What are **Smart Contracts?**
<br>
Smart Contracts are peer-to-peer digital user agreements on the blockchain. To write Smart contracts in Ethereum we use solidity programming language.


What is **Web3.js?**
<br>
Web3.js is a set of JavaScript libraries that acts like a port to the blockchain world. Web3 is a medium to connect our Smart Contracts to the front-end of the DApp.

In this section, I introduced you to the basics of technology that we're going to use and roadmap of our DApp, now the interesting part. Let's make our DApp!

## Project Setup
To build the DApp without dealing with any annoying version errors & instead of installing each dependency one-by-one, we'll start building our DApp by installing all the necessary dependencies by cloning the GitHub repository.
<br>
Clone/download the GitHub repository from https://github.com/AkhileshThite/DTube.
<br>
`git clone https://github.com/AkhileshThite/DTube.git` this command will copy the folder from git on your computer.
<br>
`cd [repo_name]` this command will open that repo you just copied from GitHub.
<br>
Now, open the folder with your favorite IDE, I'm using VS Code.

<div align="center"><img src="https://user-images.githubusercontent.com/68826419/129099717-a0445e67-98d3-4269-a7e4-d11b92a356fa.png" /></div>

Install all the dependencies by the following command:
<br>
`npm install`
<br>
Note:- As the tutorial moves further, for each section you can clear the code from the file and code it by yourself. You can always cross-check your code from this tutorial or the original GitHub repository of the project.
<br>
*I'll provide **path** and GitHub **repo link** on top of each section of the tutorial, so you don't need to scroll.*

## Smart Contracts in Solidity
Path:`/src/contracts/DTube.sol`


We are going to design Smart Contracts to upload videos (With IPFS video hash), Store videos (With the title and IPFS video hash), list videos (by video IDs) to the blockchain.
<br>
Let's define the version of solidity and create a contract called DTube. Initially, we're saying that the video count is zero. `uint` means unsigned integer (Positive number) data type. `string` means char data type. We'll call this contract later on by the name "DTube" with the help of ABI. The state variable `public` doesn't have to do anything with security. `mapping(uint => Video) public videos` this is how the mapping is done in solidity, for multiple videos we're creating a variable `Videos` by using the data type of each element `Video` which we'll create in the next code snippet.
```solidity
pragma solidity ^0.5.0;

contract DTube {
  uint public videoCount = 0;
  string public name = "DTube";
  mapping(uint => Video) public videos;
```
Now, let's create `Video` data types and `VideoUploaded` event.
```solidity
// Create data types
  struct Video {
    uint id;    // video count
    string hash; // IPFS video hash
    string title; // Title of the video
    address author; // User's wallet address
  }
// Create an event
  event VideoUploaded(
    uint id,
    string hash,
    string title,
    address author
  );
```
Let's create a `uploadVideo` function with two arguments `_videoHash` and `_title`, inside the function we're making sure the `video hash`, `video title`, `uploader address` exists by using some conditions (length should be greater than zero). After that, to list down the videos we'll increase the video count (videoCount = videoCount + 1).
```solidity
  constructor() public {
  } 
  
  function uploadVideo(string memory _videoHash, string memory _title) public {
    // Make sure the video hash exists
    require(bytes(_videoHash).length > 0);
    // Make sure video title exists
    require(bytes(_title).length > 0);
    // Make sure uploader address exists
    require(msg.sender!=address(0));

    // Increment video id
    videoCount ++;
```
Finally, we'll add the video to the contract by including `videoCount`,`_videoHash`, `_title`, `msg.sender`(which is global variable in solidity, it simply means the current user) variables. Then we'll create a function `VideoUploaded` to trigger the event.
```solidity
    // Add video to the contract
    videos[videoCount] = Video(videoCount, _videoHash, _title, msg.sender);
    // Trigger an event
    emit VideoUploaded(videoCount, _videoHash, _title, msg.sender);
  }
}
```

## Truffle Migrations
Path:`/src/contracts/`
<br>
Path:`/migrations/`


Whenever we create a DApp using truffle by the commands `truffle init` or `truffle unbox react`, truffle gives us boilerplate code to start building our DApp. It contains the following main files:

`migrations/1_initial_migration.js`
<br>
`contracts/Migrations.sol (& DTube.sol)`
<br>
`test`
<br>
`truffle-config.js`
<br>
*(We'll understand and see `truffle-config.js` at the time of deployment of our Smart Contracts.)*


**Migrations are JavaScript files that help you deploy contracts to the Ethereum network. These files are responsible for staging your deployment tasks, and they're written under the assumption that your deployment needs will change over time.**


Hence, to deploy our Smart Contracts to the Blockchain it is important to create a new file in the migrations folder called `2_initial_migration.js` which will talk to our `DTube.sol` contracts.

<div align="center"><img src="https://user-images.githubusercontent.com/68826419/129098791-50cf3734-1b9c-4391-bfab-1d7b08e20b1a.png" /></div>

The code is similar to `1_initial_migration.js`, just replace migrations with DTube.
<br>
`2_initial_migration.js` will look like this:
```javascript
const DTube = artifacts.require("DTube");

module.exports = function(deployer) {
  deployer.deploy(DTube);
};
```

## Front-end with React.js
Path: `/src/components/`


React applications are broken into components like for example navigation bar, main page, footer of the webpage. React loads a single HTML page (`/public/index.html`) which is connected with all the components. That's the reason everything loads so fast in react.

<div align="center"><img src="https://user-images.githubusercontent.com/68826419/129173906-a0da9cb6-680d-4caf-b448-d4d57cef3755.png" /></div>

### app.js
Now let's work on our main `app.js` file which will contain all the components (navbar, main, footer).

First, let's import all the components, Web3 and declare IPFS.
```javascript
import React, { Component } from 'react';
import DTube from '../abis/DTube.json'
import Navbar from './Navbar'
import Main from './Main'
import Footer from './Footer'
import Web3 from 'web3';
import './App.css';

//Declare IPFS
const ipfsClient = require('ipfs-http-client')
const ipfs = ipfsClient({ host: 'ipfs.infura.io', port: 5001, protocol: 'https' })
```
After that we're going to paste the exact default code which MetaMask instructs us to load web3. It takes Ethereum provider from MetaMask and injects it to your DApp, if your browser does not have MetaMask installed then it will show a pop up "Non-Ethereum browser detected. You should consider trying MetaMask!" message.


About Async/Await Function in JavaScript:
<br>
**Async:**
It simply allows us to write promises based code as if it was synchronous and it checks that we are not breaking the execution thread. It operates asynchronously via the event-loop. Async functions will always return a value. It makes sure that a promise is returned and if it is not returned then javascript automatically wraps it in a promise which is resolved with its value.
<br>
**Await:**
Await function is used to wait for the promise. It could be used within the async block only. It makes the code wait until the promise returns a result. It only makes the async block wait.

You can find simple explanation of Async/Await Function [here](https://www.geeksforgeeks.org/async-await-function-in-javascript/).

```javascript
class App extends Component {

  async componentWillMount() {
    await this.loadWeb3()
    await this.loadBlockchainData()
  }

  async loadWeb3() {
    if (window.ethereum) {
      window.web3 = new Web3(window.ethereum)
      await window.ethereum.enable()
    }
    else if (window.web3) {
      window.web3 = new Web3(window.web3.currentProvider)
    }
    else {
      window.alert('Non-Ethereum browser detected. You should consider trying MetaMask!')
    }
  }
```
In `loadBlockchainData()` function, we're going to load the ETH accounts, connect with the network ID, list down the videos by the newest. If the smart contracts are not deployed to the respective network, then it'll show a pop up "DTube contract not deployed to detected network." message.
<br>
React components has a built-in state object. The state object is where you store property values that belongs to the component. When the state object changes, the component re-renders. We'll use `this.state` to fetch the blockchain data and display it in our front-end react components later with `this.props`.
```javascript
  async loadBlockchainData() {
    const web3 = window.web3
    // Load account
    const accounts = await web3.eth.getAccounts()
    this.setState({ account: accounts[0] })
    // Network ID
    const networkId = await web3.eth.net.getId()
    const networkData = DTube.networks[networkId]
    if(networkData) {
      const dtube = new web3.eth.Contract(DTube.abi, networkData.address)
      this.setState({ dtube })
      const videosCount = await dtube.methods.videoCount().call()
      this.setState({ videosCount })
      // Load videos, sort by newest
      for (var i=videosCount; i>=1; i--) {
        const video = await dtube.methods.videos(i).call()
        this.setState({
          videos: [...this.state.videos, video]
        })
      }
      //Set latest video with title to view as default 
      const latest = await dtube.methods.videos(videosCount).call()
      this.setState({
        currentHash: latest.hash,
        currentTitle: latest.title
      })
      this.setState({ loading: false})
    } else {
      window.alert('DTube contract not deployed to detected network.')
    }
  }
```

Now we're going to prepare the file for upload to IPFS by `captureFile` function.

```javascript
  captureFile = event => {
    event.preventDefault()
    const file = event.target.files[0]
    const reader = new window.FileReader()
    reader.readAsArrayBuffer(file)

    reader.onloadend = () => {
      this.setState({ buffer: Buffer(reader.result) })
      console.log('buffer', this.state.buffer)
    }
  }
```
Let's upload the file to IPFS by `uploadVideo` function. While uploading a video file to IPFS it'll show a message in the console "Submitting file to IPFS...". Here, we're adding the file to IPFS with `ipfs.add()` function which will take two arguments -> file & callback. After that we're going to store the IPFS hash of the video file to the blockchain.
```javascript
  uploadVideo = title => {
    console.log("Submitting file to IPFS...")
    //adding file to the IPFS
    ipfs.add(this.state.buffer, (error, result) => {
      console.log('IPFS result', result)
      if(error) {
        console.error(error)
        return
      }

      this.setState({ loading: true })
      //adding IPFS video hash to the blockchain.
      this.state.dtube.methods.uploadVideo(result[0].hash, title).send({ from: this.state.account }).on('transactionHash', (hash) => {
        this.setState({ loading: false })
      })
    })
  }
```
To update the video hash and title of the video we're going to create `changeVideo` function and pass currentHash and currentTitle. After that, let's create bind functions to display the blockchain data in our front-end react components.
<br>
The bind() is an inbuilt method in React that is used to pass the data as an argument to the function of a class based component.
```javascript
  changeVideo = (hash, title) => {
    this.setState({'currentHash': hash});
    this.setState({'currentTitle': title});
  }

  constructor(props) {
    super(props)
    this.state = {
      buffer: null,
      account: '',
      dtube: null,
      videos: [],
      loading: true,
      currentHash: null,
      currentTitle: null
    }

    this.uploadVideo = this.uploadVideo.bind(this)
    this.captureFile = this.captureFile.bind(this)
    this.changeVideo = this.changeVideo.bind(this)
  }
```
Finally, let's add all the components we imported at the top `<Navbar>`, `<Main>` & `<Footer>`. Remeber `this.state` is fetching all the blockchain data so that we can use that data to display in our react front-end components.
<br>
In `<Navbar>` we want to display the account address of the user, hence `<Navbar account={this.state.account} />` will fetch the current account address of the user and we'll display that in the `Navbar.js` component by `this.props.account`. Similarly for main content of our DApp we need videos, uploadVideo, captureFile, changeVideo, currentHash, currentTitle data to display it on `Main.js` component.
```javascript
  render() {
    return (
      <div>
        <Navbar account={this.state.account} />
        { this.state.loading
          ? <div id="loader" className="text-center mt-5"><p>Loading...</p></div>
          : <Main
              videos={this.state.videos}
              uploadVideo={this.uploadVideo}
              captureFile={this.captureFile}
              changeVideo={this.changeVideo}
              currentHash={this.state.currentHash}
              currentTitle={this.state.currentTitle}
            />
        }
        <Footer />
      </div>
    );
  }
}

export default App;
```
