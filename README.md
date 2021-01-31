# simple-erc20-example
Simple erc20 deployer using truffle js library.

## Quickstart
Clone this repository to your local environment.
### Create an env file
```sh
$ mv env.example .env
$ cat .env
INFURA_PROJECT_ID="xxxxxxxxxxxxxxxxxxxxxxxxx"
DEV_PRIVATE_KEY="your-ethereum-wallet-private-key-here"
ETHERSCAN_API_KEY="etherescan-api-key-here"
$ # Please update this .env file with your credentials!
```
### Add your ERC20 token smart contract
1. Add your erc20 token.
```sh
$ cd contracts
$ cp SimpleToken.sol MyToken.sol
$ # Edit MyToken.sol as required!
```
2. Edit migrations/2_deploy_token.js file and add your newly created erc20 token.
```sh
$ cat migrations/2_deploy_token.js
const SimpleToken = artifacts.require("SimpleToken");

module.exports = function(deployer) {
      deployer.deploy(SimpleToken);
};
```
### Deploy new erc20 token using truffle
1. Install dependencies.
```sh
$ npm i
```
2. Deploy new erc20 token.
```sh
$ truffle migrate --network rinkeby # This will deploy on rinkeby testnet!
```
