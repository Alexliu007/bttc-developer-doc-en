# Deploy Contract
## Deploy HelloWorld Contract with Remix
### Setting up [Remix IDE#](https://remix.ethereum.org/)
Remix is a web-based IDE for writing, compiling, and deploying smart contracts.

If this is your first time using Remix, you must locate and activate the "Solidity compiler" plug-in, as shown in the figure below.

![](https://i.imgur.com/BFprOBG.png)

By clicking the button circled in the figure, you can create a new file called HelloWorld.sol and copy and paste the following code into it.

![](https://i.imgur.com/iTedpga.png)

### HelloWorld.sol
```js
//SPDX-License-Identifier: GPL-3.0
pragma solidity ^0.8.7;

contract HelloWorld {
    string public greeting;
    
    constructor(string memory message) {
        greeting = message;
    }
    
    function updateGreeting(string memory message) public {
        greeting = message;
    }
}
```
In the first line, `SPDX-License-Identifier: GPL-3.0` specifies that this smart contract is open source and adheres to the `GPL3.0` open source agreement. You can also choose from a variety of other open-source licenses based on your specific requirements. When there is not a license, use `UNLICENSED`.

The second line, `pragma solidity ^0.8.7`, specifies the compiler's version. This contract can be successfully compiled only with the Solidity compiler version 0.8.7 or higher.

`string public greeting` declares a public variable named greeting of the string type. This variable is referred to as a state variable, and it will be stored in the contract and on the blockchain in perpetuity. The public keyword enables external access to this variable and creates an accessor function for it.

`constructor` specifies the contract's constructor. It is capable of receiving a string parameter message, storing it in memory, and assigning the message's value to `greeting`. Please keep in mind that each smart contract can only contain one constructor, which will be invoked only when the contract is deployed.

`function updateGreeting` declares an ordinary function that can be called from outside to modify the content of greeting.
### Compile Smart Contract
Select the Solidity compiler on the left, and select version 0.8.7 or higher.

Click Compile HelloWorld.sol. When the compilation is successful, the compiler icon will have a green tick, as shown in the figure.

![](https://i.imgur.com/XNYEsGM.png)

### Network settings

Open the MetaMask wallet and select Custom RPC in the drop-down menu as shown in the figure

![](https://i.imgur.com/RzNmbtC.png)

Fill in according to the information in the picture:
* Network Name: BitTorrent Chain Donau
* RPC URL: https://pre-rpc.bt.io/ 
* ChainID: 1029
* Symbol: BTT
* Block Explorer URL: https://testscan.bt.io/

![](https://i.imgur.com/5f34Tme.png)

The screen after the addition is complete is shown below

![](https://i.imgur.com/p6pGbpF.png)

The test account has been pre-funded with some test coins. Kindly visit the faucet to obtain a test BTT.

Once the network configuration is complete, the smart contract can be deployed on BTTC.

### Deployment contracts
First, in the DEPLOY & RUN TRANSACTIONS column of Remix, select Injected Web3 from the Environment drop-down menu

![](https://i.imgur.com/zG0J7ge.png)

In the input box next to Deploy, enter the initial Greeting content

![](https://i.imgur.com/rZzofHN.png)

After clicking Deploy, MetaMask will pop up a transaction confirmation window

![](https://i.imgur.com/j5fSmxg.png)

Congratulations! The HelloWorld contract has been successfully deployed to the BTTC testnet. Now you can interact with it and check its status on the explorer.

![](https://i.imgur.com/DIxheNu.png)
