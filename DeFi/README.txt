1.Project Purpose


This project is a Decentralized Finance (DeFi) contract and frontend application that allows users to invest (sepolia)ETH, withdraw ETH and receive dividends based on their investment.
The contract manages investments, calculates dividends, and ensures fair distribution among investors.

Technologies Used:

Solidity: Smart contract programming language used for writing the Ethereum smart contract.
Ethereum (Sepolia testnet): Blockchain platform for deploying the smart contract and making transactions.
Ethers.js: JavaScript library for interacting with Ethereum.
MetaMask: Browser extension for interacting with Ethereum dApps.
HTML/CSS: For building the frontend user interface.



#######################



2.Smart Contract Documentation


Functions:


invest()
Description: Allows users to make an investment by sending ETH to the contract.
Input: ETH (in wei) to invest.
Output: Updates user’s balance and the contract’s total invested amount.


withdraw(uint256 amount)
Description: Allows users to withdraw a specific amount of their investment.
Input: Amount (in wei) to withdraw.
Output: Updates user’s balance and transfers ETH to the user.


distributeDividends()
Description: Allows the contract owner to distribute dividends based on the available funds. Dividend percentage is set by owner prior to deployment on the blockchain.
Output: Distributes dividends proportionally to the investors based on their share of the total invested amount.


deposit()
Description: Allows the contract owner to deposit additional funds into the contract, this is to act as generated profit so that investors can receive their dividends.
Input: ETH (in wei) to deposit.
Output: Increases the total amount and updates the owner’s balance.


getUserBalance()
Description: Returns the balance of the caller (the user’s investment amount).
Output: User’s current balance in the contract (in wei).


getTotalBalance()
Description: Returns the total balance of the contract (in wei).
Output: Total contract balance (in wei).


owner()
Description: Returns the address of the contract owner.
Output: The owner’s Ethereum address.



#######################



3.Frontend Documentation


User Interface (UI)
The frontend is a web interface that allows users to interact with the contract:

Investment Section:
Amount Input: Users enter the amount of ETH to invest.
Invest Button: Users click to send the investment to the contract.


Withdrawal Section:
Amount Input: Users enter the amount of ETH to withdraw.
Withdraw Button: Users click to withdraw funds from the contract.


Balance Display:
Shows the contract’s total balance in ETH.


Distribute Dividends Section:
Visible only to the contract owner. Allows the owner to distribute dividends to investors.


Deposit Section:
Visible only to the contract owner. Allows the owner to deposit additional ETH into the contract.



#######################



Setup:

1.Install MetaMask:https://metamask.io/download/
2.Switch to sepolia testnet(11155111), you can find this on https://chainid.network/ then enter "sepolia" into the search bar then click connect to "Sepolia" Chain ID 11155111.
3.Get SepoliaETH, https://cloud.google.com/application/web3/faucet/ethereum/sepolia, enter your wallet address, select sepolia network and click "Recieve 0.05 Sepolia ETH".
4.Run DeFi/FrontEnd/index.html on your preferred code editor, in my case I used VS code. 
(if using VS code, you can install live server extension and then right click anywhere in the code and click "Open with live server" to run an instance).
5.Upon running index.html, you will automatically be prompted to connect to the site with MetaMask.
6.The smart contract "0x97a2cc557d2f648a33f8055ddc7bc3cbc831d7f5" (InvestmentFund) is already deployed on the sepolia testnet and is verified.


(If you would like to deploy your own version of the smart contract:
1.go to remix.ethereum.org, 
2.in File Explorer under contracts folder, 
3.create a new file file-name.sol and paste the contents of DeFi/SmartContract/InvestmentFund.txt into your file,
4.go to Solidity Compiler and select version 0.8.26 from the drop down list,
5.click compile,
6.go to Debug & run transactions,
7.under Enviroment, select WalletConnect from the drop down list, MetaMask will be prompted to connect to the site, 
once connected you should see Sepolia (11155111) network shown underneath the Enviorment,
8.in the input field for the button deploy, set the distributeDividends percentage 1-9999, in my case i entered 500 to set the percentage to 5%,
9.click deploy,
10.once deployed, copy contract address from the terminal and paste it in the const contractAddress =your-contract-address field, this is to ensure the front end is interacting with your contract,
you can now interact with your contract directly in remix or using the front end.)



Investor Interaction:

To invest, enter an amount in ETH into the input field above the invest button then click invest, 
you will be prompted by MetaMask to confirm transaction, click confirm and your account balance and contract balance will be updated.

To withdraw, enter an amount in ETH into the input field above the withdraw button then click withdraw, 
you will be prompted by MetaMask to confirm transaction, click confirm and your account balance and contract balance will be updated.

To view the total ETH balance in the contract, click Get Contract Balance and it will return the total contract balance.


Owner Interaction:

If connected to the site as the contract owner:

To distribute dividends to the investors, click Distribute Dividends, 
you will be prompted to confirm transaction by MetaMask, click confirm, investors wallet balances will be updated.

To deposit into the contract, enter an amount in ETH in the input field above the deposit button and click deposit,
you will be prompted to confirm transaction by MetaMask, click confirm.
