# Build a Social Media DApp & Deploy it on Polygon
<div align="center"><img src="https://user-images.githubusercontent.com/68826419/128836864-2f40f55f-66fd-4f79-822f-883ad1d03106.png" /></div>


## Introduction
In this tutorial, I'll show you how to Build a Social Media DApp (Decentralized Apllication) just like YouTube & how to Deploy it on Polygon (Matic) Mumbai Test Network.<br>
I'll start the tutorial from scratch (MetaMask installation process to hosting the DApp on IPFS using Fleek).<br>
So, grab a cup of coffee ☕️ and let's get started!


*About this project: DTube was created by me during the ETHOdyssey Virtual Hackathon in July-Aug 2021. All the resources I used to create this DApp are linked at the bottom "References" section*

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
Done! check your wallet, you'll see some Matic there.
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
We are going to use solidity language to write Smart Contracts, What are **Smart Contracts?**
<br>
Smart Contracts are peer-to-peer digital user agreements on the blockchain. To write Smart contracts in Ethereum we use solidity programming language.
<br>
First, we'll setup our coding environment with the help of **Truffle**, after that we'll write **Smart Contracts** in **solidity**. 
After writing Smart Contracts, To build the front-end of our DApp we'll use **React.js** Javascript library plus some **HTML5, CSS3 & JavaScript**.
<br>
We're going to use **IPFS** (InterPlanetary File System) to store the hashes of our videos to the blockchain and later we'll be able to play those videos by calling those video hashes.
<br>
To connect our Smart Contracts with fron-end we'll use **Web3.js** and then we'll deploy our Smart Contracts on **Polygon (Matic) Mumbai Test Network**. In the final step, we'll host this DApp on IPFS by using the **Fleek** platform.

In this section, I introduced you to the basics of technology that we're going to use and roadmap of our DApp, now the interesting part. Let's make our DApp!

## Project Setup
To build the DApp without dealing with any annoying version errors & instead of installing each dependency one-by-one, we'll start building our DApp by installing all the necessary dependencies by cloning the GitHub repository.
<br>
Clone/download the GitHub repository from [here](https://github.com/AkhileshThite/DTube).
<br>
`git clone https://github.com/AkhileshThite/DTube.git` this will copy the folder from git on your computer.
<br>
`cd [repo_name]` this will open that repo you just copied from GitHub.
<br>
Now, open the folder with your favorite IDE, I'm using VS Code.

<div align="center"><img src="https://user-images.githubusercontent.com/68826419/128924693-5b541c00-b990-45f5-ada4-671e81a8ddc6.png" /></div>

Install all the dependencies by the following command:
`npm install`
<br>
Note:- As the tutorial moves further, for each section you can clear the code from the file and code it by yourself. You can always cross-check your code from this tutorial or the original GitHub repository of the project.
<br>
*I'll provide **path** and GitHub **repo link** on top of each section of the tutorial, so you don't need to scroll.*

## Writing Smart Contracts in Solidity
Path:`/src/contracts/DTube.sol`
### Data Structure:
We are going to design Smart Contracts to upload videos (With IPFS video hash), Store videos (With the title and IPFS video hash), list videos (by video IDs) to the blockchain.
<br>
Let's define the version of solidity and create a contract called DTube. Initially, we're saying that the video count is zero. `uint` means unsigned integer (Positive number) data type. `string` means char data type. We'll call this contract later on by the name "DTube". The state variable `public` doesn't have to do anything with security. `mapping(uint => Video) public videos` this is how the mapping is done in solidity, for multiple videos we're creating a variable `Videos` by using the data type of each element `Video` which we'll create in the next code snippet.
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
Let's create a `uploadVideo` function, inside the function we're making sure the `video hash`, `video title`, `uploader address` exists by using some conditions (length should be greater than zero). After that, to list down the videos we'll increase the video count (videoCount = videoCount + 1).
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
Finally, we'll add the video to the contract by including `videoCount`,`_videoHash`, `_title`, `msg.sender`(which is global variable in solidity, it simply means the current user). Then we'll create a function `VideoUploaded` to trigger that event.
```solidity
    // Add video to the contract
    videos[videoCount] = Video(videoCount, _videoHash, _title, msg.sender);
    // Trigger an event
    emit VideoUploaded(videoCount, _videoHash, _title, msg.sender);
  }
}
```
