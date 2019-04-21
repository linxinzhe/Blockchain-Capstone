# Udacity Blockchain Capstone

The capstone will build upon the knowledge you have gained in the course in order to build a decentralized housing product. 

## Install
```
npm install -g ganache-cli
npm install .
```

## Testing
```
ganache-cli -m "candy maple cake sugar pudding cream honey rich smooth crumble sweet treat"
npm run compile
npm run test-erc721
npm run test-square-verifier
npm run test-soln-square-verifier
```

## ZoKrates
```
docker run -v ~/github/Blockchain-Capstone/zokrates/code:/home/zokrates/code -ti zokrates/zokrates /bin/bash
cd code/square
~/zokrates compile -i square.code
~/zokrates setup
~/zokrates compute-witness -a 3 9
~/zokrates generate-proof
~/zokrates export-verifier
```

## Deployment
1. Go to [Infura](https://infura.io/) to create an account for creating a project.
2. Get the ENDPOINT url for Rinkeby test network.
3. Get the test ETH from [faucet.rinkeby.io](https://faucet.rinkeby.io.)
4. Config truffle-config.js with Infura ENDPOINT
5. Run `npm run deploy`

Deploy result
```
   Deploying 'RealEstateERC721Token'
   > contract address:    0x846eF385549Ee30165eD2B51f8437EE41dEfb99A

   Deploying 'SquareVerifier'
   > contract address:    0xCFE6ba31934D78f75d0C7829DE213a35e7BCB8cd

   Deploying 'SolnSquareVerifier'
   > contract address:    0x7190a33E02E110eB5A231A348F5F268ad23a54a7

```

Contract ABI (xxxxx.json) located in build/contracts

## Mint token
1. Go to [Remix - Solidity IDE](https://remix.ethereum.org/)
2. Choose injected web3 and copy contract address to "At address"
3. Mint 10 token according to proof.json and tokenid is from 1 to 10

Result:
Total Supply: 10 RE https://rinkeby.etherscan.io/token/0x846eF385549Ee30165eD2B51f8437EE41dEfb99A

## Opensea storefront


## Project Resources

* [Remix - Solidity IDE](https://remix.ethereum.org/)
* [Visual Studio Code](https://code.visualstudio.com/)
* [Truffle Framework](https://truffleframework.com/)
* [Ganache - One Click Blockchain](https://truffleframework.com/ganache)
* [Open Zeppelin ](https://openzeppelin.org/)
* [Interactive zero knowledge 3-colorability demonstration](http://web.mit.edu/~ezyang/Public/graph/svg.html)
* [Docker](https://docs.docker.com/install/)
* [ZoKrates](https://github.com/Zokrates/ZoKrates)