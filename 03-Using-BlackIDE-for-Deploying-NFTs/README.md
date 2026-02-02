
# Using Black IDE to Deploy NFTs on BSC

In this tutorial, we provide a step-by-step guide to the readers on how to issue Non-fungible tokens (NFTs) (ERC721/1155) on the BNB Smart Chain (BSC) Testnet using the Black IDE. This is a detailed guide to learning how to issue, mint and transfer NFTs on the BSC Testnet. The technology stack used in this tutorial includes Solidity , Truffle, MetaMask, and BlackIDE. 

## Learning Takeaways:
This tutorial will help you gain knowledge on the following learning points:
-	Using BlackIDE for smart contract development;
-	Managing Keypairs and Funding BNB Tokens to your account on BlackIDE;
-	MetaMask Wallet connectivity to BSC Testnet;
-	Smart-contract development;
-	Issuing, minting, and transferring NFTs;

## Technology Stack Details
-	BlackIDE (latest version recommended)
-	Truffle v5.11.x or higher
-	MetaMask Wallet (latest version recommended)
-	Docker (latest version recommended)

## Brief Introduction Tech Stack
1.	**Solidity:** one of the most popular object-oriented high-level smart contract programming languages. For more details on Solidity, refer here.
2.	**MetaMask Wallet Browser Extension:** we recommend using the Metamask Chrome extension. It is a web wallet that allows connecting the chrome browser to any valid blockchain network.
3.	**Black IDE:** Black IDE is an integrated development environment (IDE), making developing EVM-compatible smart contracts faster and easier. Black IDE offers both desktop and web (Black IDE Web) applications.

## Setting up the Environment
We aim to keep this tutorial as simple as possible and hence tend to use as minimal resources as possible and have used the following tools in this tutorial.
*	Metamask Wallet
*	Ensure that you have the Metamask Wallet extension installed and running on our browser.
*	Configure the Metamask wallet for use with the BSC Testnet. Use the following details to add the BSC Testnet. For further details, refer here.
*	Network Name: BSC Testnet
*	RPC URL: (configure as needed)
*	Chain ID: 97
*	Currency Symbol: BNB
*	Block Explorer URL: (configure as needed) 
*	Black IDE: both desktop app and web app are available and it is up to your convenience to choose from. For this tutorial, we used the desktop app as the web app lacks support for importing OpenZeppelin Contracts. 
*	Download/Install any dependencies required by BlackIDE



## Login into Black IDE
1.	Open the Black IDE desktop application. We will be using it for compiling and deploying our smart contract for NFTs on the BSC Testnet.
2.	Click on the Login button and authorize using your GitHub account.



## Create New Project
3.	Click on the New button next to the projects to create a new project. 



4.	Specify the location where you want to save your project on your device, the project name, e.g. “BSC-NFT”, and select the project type from the dropdown list as “Basics- ERC20, ERC721, & ERC1155 (v31+)”. Then click the Create button to create the project.



5.	Remember the smart contract in this tutorial is just a sample, you can always modify and be innovative.

## Smart Contract Creation 
6.	Expand the contracts menu and delete the default files. 



7.	Right-click on the contracts menu and select New File. Specify a name for your file, e.g., BSC-NFT.sol, and then click Create button.



## Write your smart contract code
8.	Copy the following code into your smart contract file. We have used the contract code from the ERC721_NFT.sol file in this repo.
9.	Remember to change the ```MINT_PRICE```, ```MAX_SUPPLY```, ```name```, and ```symbol``` of the token as per your need. Also, remember to change the ```_baseURI``` as per your token.
10.	


## Edit default project settings
10.	Click on the config.json file to change the default setting. Change the main file name to the name of your contract, BSC-NFT.sol in our case. Similarly, change the name of the smart contract to deploy, BSCNFT.json in our case. 


 
## Connect the Black IDE to the BSC Testnet
11.	In order to connect the Black IDE to the BSC Testnet, click on the dropdown icon on the network menu in the top right corner and then select Testnet under the BNB Chain label.



12.	Click on the  icon in the bottom left corner of the IDE to generate new keypair to perform transactions. You can skip this step if you already have generated a keypair. On the Keypair Manager, click on the CREATE button to generate new keypair.



13.	Specify your desired name for the keypair, in our case BSC-Testnet-Key. Then click on the CREATE button. Remember to keep your private keys securely and not share them with anyone.



## Acquire BNB Test Tokens
*	Initially, the balance of a newly created key pair is 0.0 ETH. To get BNB test tokens, you can use the BSC Testnet Faucet.
*	Copy your public address from the keypair manager



*	Paste this on the facet and acquire test tokens as required, as shown below. A green pop-up is displayed on the successful transfer of test tokens.


 
*	 Close and re-open keypair manager to verify that the balance has been updated. Wait for approx. 1-2 mins for balance to get updated.



## Deploy Smart Contract on BSC Testnet
1.	Select the appropriate Solidity compiler version from the bottom right corner of the IDE, Solc (0.8.4), 
in our case. 
2.	Click on the Build icon  to build your smart contract. Upon successful build, the project navigation pane reflects a new folder named build. This folder contains contracts folder that has json files of the contracts built. All of the contracts imported in our BSCNFT contract are also built and imported as json files. 



3.	After successfully building your contract, it’s time to deploy the contract. Click on the Deploy icon  for deploying your smart contract. Specify the details for your contract, as shown below, then click on the Estimate & Deploy button. The wizard will auto-estimate and fill the gas limit for your contract. Then click the Deploy button. 




4.	Deployment details will pop-up, as shown in the figure below.



5.	The status of the transaction will be updated to confirmed after the transaction is confirmed as shown in the figure below



6.	You can also view this transaction by clicking on the transaction icon in the bottom left on the IDE.



## Interact with deployed smart contract and Mint NFTs
1.	You can also interact with the contract using the different functions. Click on the Transactions Icon on the bottom-left corner of the IDE and then transaction of deployment of your smart contract. On the transaction details, click on the contract address to access the functions to interact with the smart contract. The left most column has all the Write Functions. The middle column has the View Functions and the right most column has the Events details.


 
## Mint NFTs
1.	As per our smart contract, when the contract is deployed, unless the NFTs are minted they won’t be visible in the wallet. 
2.	Create another keypair as defined previously. We will be issuing i.e. minting NFTs to the public address of this new keypair.
3.	To mint i.e. issue an NFT to a specific user we use the “safeMint” function of the deployed smart contract. As shown in Steps 1 and 2 in the figure below, navigate to the deployed contracts, then in the left-most column click the drop-down menu to view the list of write functions available for use with the deployed contract. Select the “safeMint” function. 
4.	Use the safeMint function to mint new NFTs to a specific user address. As shown in figure above, steps 3 to 6, enter the “ETH to send” as the minting price of NFT, as per our smart contract the minting price is 50000000000000000 Wei, i.e., 0.05 ETH. We entered 0.06 ETH to cover the transaction charges as well. Then select the address to whom you want to issue (mint) an NFT to. Here, for the To address use the newly generated keypair in the section above. After this, click the transact button  to execute the safeMint function. For the Signer, ensure that you are using the account that was used to deploy the smart contract. 



5.	To confirm what transfers have occurred, execute the Transfer event from the right most column. This will display the list of NFT transfers along with NFT token id, as shown in the figure below.



6.	To confirm owner of an NFT, use the ownerOf function. Pass the token id as input to the function, as illustrated in the figure below.



## View Your NFTs in Metamask Wallet
1.	On the receiving end, the user can import the NFT token details into their Metamask wallet to view the assets. Please note that currently, Metamask Web Extension does not support the use of NFTs however, the mobile app version does support it. For the next steps to view the owned NFTs in your Metamask wallet, we will be using the Metamask Mobile Application.
2.	Open Keypair manager on the Black IDE and copy the private key of the keypair that you minted i.e., transfer NFT.



3.	On the Metamask wallet mobile app, import an account using this key pair. Enter the private key copied in the previous step and click import.



4.	After importing account, the next step is to add the BSC Testnet configuration to the wallet. Ensure that you are using the same account whose pubic address was issued the NFT.



5.	Ensure that your account is connected to the BSC Testnet. Also, ensure that you have enough BNB test tokens in your account. If not, you can use the BSC Testnet Faucet to acquire some, as mentioned earlier.


 
6.	To view the owned NFT assets your Metamask Mobile Wallet, click on the NFTs tab and then on the Import Tokens. Fill in the NFT details. In the address field, pass the address of the deployed contract and in the Id field pass the tokenID. Then click the Import button.



## Conclusion 
In this tutorial, we provided a step-to-step guide on how to issue, mint and transfer NFTs on the BSC Testnet using the BlackIDE from Obsidian Labs. The technology stack used in this tutorial includes Solidity, Truffle, MetaMask, and BlackIDE.

