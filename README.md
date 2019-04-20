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
   Deploying 'SquareVerifier'
   > contract address:    0x48f564377bd8Cb144e2D2EdF65bA4542D3c9B123

   Deploying 'SolnSquareVerifier'
   > contract address:    0x76A04e504CF05950d5e0F5c2B1922d7611f181DC

```

##### Deployment Log 
```
/usr/local/bin/node /usr/local/lib/node_modules/npm/bin/npm-cli.js run deploy --scripts-prepend-node-path=auto

> capstone@1.0.0 deploy /Users/linxinzhe/github/Blockchain-Capstone
> truffle migrate --network rinkeby --reset --compile-all

Compiling ./contracts/ERC721Mintable.sol...
Compiling ./contracts/Migrations.sol...
Compiling ./contracts/Oraclize.sol...
Compiling ./contracts/SolnSquareVerifier.sol...
Compiling ./contracts/Verifier.sol...
Compiling ./contracts/verifier.sol...
Compiling openzeppelin-solidity/contracts/drafts/Counters.sol...
Compiling openzeppelin-solidity/contracts/math/SafeMath.sol...
Compiling openzeppelin-solidity/contracts/token/ERC721/IERC721Receiver.sol...
Compiling openzeppelin-solidity/contracts/utils/Address.sol...

Compilation warnings encountered:

/Users/linxinzhe/github/Blockchain-Capstone/contracts/Oraclize.sol:371:5: Warning: Function state mutability can be restricted to pure
    function __callback(bytes32 _myid, string memory _result, bytes memory _proof) public {
    ^ (Relevant source part starts here and spans across multiple lines).

Writing artifacts to ./build/contracts

⚠️  Important ⚠️
If you're using an HDWalletProvider, it must be Web3 1.0 enabled or your migration will hang.


Migrations dry-run (simulation)
===============================
> Network name:    'rinkeby-fork'
> Network id:      4
> Block gas limit: 7006834


1_initial_migration.js
======================

   Deploying 'Migrations'
   ----------------------
   > account:             0x627306090abaB3A6e1400e9345bC60c78a8BEf57
   > balance:             2.994898275
   > gas used:            258162
   > gas price:           10 gwei
   > value sent:          0 ETH
   > total cost:          0.00258162 ETH

   -------------------------------------
   > Total cost:          0.00258162 ETH


2_deploy_contracts.js
=====================

   Deploying 'SquareVerifier'
   --------------------------
   > account:             0x627306090abaB3A6e1400e9345bC60c78a8BEf57
   > balance:             2.976880575
   > gas used:            1774742
   > gas price:           10 gwei
   > value sent:          0 ETH
   > total cost:          0.01774742 ETH


   Deploying 'SolnSquareVerifier'
   ------------------------------
   > account:             0x627306090abaB3A6e1400e9345bC60c78a8BEf57
   > balance:             2.929980125
   > gas used:            4690045
   > gas price:           10 gwei
   > value sent:          0 ETH
   > total cost:          0.04690045 ETH

   -------------------------------------
   > Total cost:          0.06464787 ETH


Summary
=======
> Total deployments:   3
> Final cost:          0.06722949 ETH

⚠️  Important ⚠️
If you're using an HDWalletProvider, it must be Web3 1.0 enabled or your migration will hang.


Starting migrations...
======================
> Network name:    'rinkeby'
> Network id:      4
> Block gas limit: 7006834


1_initial_migration.js
======================

   Deploying 'Migrations'
   ----------------------
   > transaction hash:    0x4d5df4eeed14998e64b69ce562adf24a4ad2ed74d071f7b8da022de9e64017f0
   > Blocks: 0            Seconds: 13
   > contract address:    0xB6d4D7Fe9756677Ae5B4b4EE01159155655940f0
   > account:             0x627306090abaB3A6e1400e9345bC60c78a8BEf57
   > balance:             2.994748275
   > gas used:            273162
   > gas price:           10 gwei
   > value sent:          0 ETH
   > total cost:          0.00273162 ETH


   > Saving migration to chain.
   > Saving artifacts
   -------------------------------------
   > Total cost:          0.00273162 ETH


2_deploy_contracts.js
=====================

   Deploying 'SquareVerifier'
   --------------------------
   > transaction hash:    0xc180c5bfbf74ae0edb862ef27b8b4828d7e056b2af63eb3acdf5865e8c056166
   > Blocks: 1            Seconds: 19
   > contract address:    0x48f564377bd8Cb144e2D2EdF65bA4542D3c9B123
   > account:             0x627306090abaB3A6e1400e9345bC60c78a8BEf57
   > balance:             2.976580575
   > gas used:            1774742
   > gas price:           10 gwei
   > value sent:          0 ETH
   > total cost:          0.01774742 ETH


   Deploying 'SolnSquareVerifier'
   ------------------------------
   > transaction hash:    0x38ed7b56400e5cc8ed88d848737ef27cc9585d44ca44a17f659cd84d0c63e0ff
   > Blocks: 2            Seconds: 20
   > contract address:    0x76A04e504CF05950d5e0F5c2B1922d7611f181DC
   > account:             0x627306090abaB3A6e1400e9345bC60c78a8BEf57
   > balance:             2.928078125
   > gas used:            4850245
   > gas price:           10 gwei
   > value sent:          0 ETH
   > total cost:          0.04850245 ETH


   > Saving migration to chain.
   > Saving artifacts
   -------------------------------------
   > Total cost:          0.06624987 ETH


Summary
=======
> Total deployments:   3
> Final cost:          0.06898149 ETH


Process finished with exit code 0


```

## Project Resources

* [Remix - Solidity IDE](https://remix.ethereum.org/)
* [Visual Studio Code](https://code.visualstudio.com/)
* [Truffle Framework](https://truffleframework.com/)
* [Ganache - One Click Blockchain](https://truffleframework.com/ganache)
* [Open Zeppelin ](https://openzeppelin.org/)
* [Interactive zero knowledge 3-colorability demonstration](http://web.mit.edu/~ezyang/Public/graph/svg.html)
* [Docker](https://docs.docker.com/install/)
* [ZoKrates](https://github.com/Zokrates/ZoKrates)
