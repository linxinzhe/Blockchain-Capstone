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
   > contract address:    0x3f0DDd99ea6c8026bE34463aae6Aa621f39fE60D

   Deploying 'SolnSquareVerifier'
   > contract address:    0x598535260F85fE7E5DdB729c9a8248dF7f7FaC2e

```

## Mint token
1. Go to [Remix - Solidity IDE](https://remix.ethereum.org/)
2. Choose injected web3 and copy contract address to "At address"
3. Mint 10 token according to proof.json and tokenid is from 1 to 10

## Project Resources

* [Remix - Solidity IDE](https://remix.ethereum.org/)
* [Visual Studio Code](https://code.visualstudio.com/)
* [Truffle Framework](https://truffleframework.com/)
* [Ganache - One Click Blockchain](https://truffleframework.com/ganache)
* [Open Zeppelin ](https://openzeppelin.org/)
* [Interactive zero knowledge 3-colorability demonstration](http://web.mit.edu/~ezyang/Public/graph/svg.html)
* [Docker](https://docs.docker.com/install/)
* [ZoKrates](https://github.com/Zokrates/ZoKrates)

### Deployment Log
```
/usr/local/bin/node /usr/local/lib/node_modules/npm/bin/npm-cli.js run deploy --scripts-prepend-node-path=auto

> capstone@1.0.0 deploy /Users/linxinzhe/github/Blockchain-Capstone
> truffle migrate --network rinkeby --reset --compile-all

Compiling ./contracts/ERC721Mintable.sol...
Compiling ./contracts/Migrations.sol...
Compiling ./contracts/Oraclize.sol...
Compiling ./contracts/SolnSquareVerifier.sol...
Compiling ./contracts/Verifier.sol...
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
> Block gas limit: 7002635


1_initial_migration.js
======================

   Replacing 'Migrations'
   ----------------------
   > account:             0x627306090abaB3A6e1400e9345bC60c78a8BEf57
   > balance:             2.919014656
   > gas used:            258162
   > gas price:           10 gwei
   > value sent:          0 ETH
   > total cost:          0.00258162 ETH

   -------------------------------------
   > Total cost:          0.00258162 ETH


2_deploy_contracts.js
=====================

   Replacing 'SquareVerifier'
   --------------------------
   > account:             0x627306090abaB3A6e1400e9345bC60c78a8BEf57
   > balance:             2.900996956
   > gas used:            1774742
   > gas price:           10 gwei
   > value sent:          0 ETH
   > total cost:          0.01774742 ETH


   Replacing 'SolnSquareVerifier'
   ------------------------------
   > account:             0x627306090abaB3A6e1400e9345bC60c78a8BEf57
   > balance:             2.854096506
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
> Block gas limit: 6996225


1_initial_migration.js
======================

   Replacing 'Migrations'
   ----------------------
   > transaction hash:    0xe014267dd6cb43a8c7f81a012192539b192e36fe98c864ce3517d6971adad1c3
   > Blocks: 1            Seconds: 17
   > contract address:    0x7F1Eb78b81432F2Ef710BC77f9761347C4922e2C
   > account:             0x627306090abaB3A6e1400e9345bC60c78a8BEf57
   > balance:             2.918864656
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

   Replacing 'SquareVerifier'
   --------------------------
   > transaction hash:    0xf603e23d6f647771c02d2df0f57970e6437489d3ef56b3ab1099c79a435302b3
   > Blocks: 2            Seconds: 28
   > contract address:    0x3f0DDd99ea6c8026bE34463aae6Aa621f39fE60D
   > account:             0x627306090abaB3A6e1400e9345bC60c78a8BEf57
   > balance:             2.900696956
   > gas used:            1774742
   > gas price:           10 gwei
   > value sent:          0 ETH
   > total cost:          0.01774742 ETH


   Replacing 'SolnSquareVerifier'
   ------------------------------
   > transaction hash:    0xf73e1b98afbf80df78bea4286e9515a52d89d336c739e590c34a2302b00dcc35
   > Blocks: 1            Seconds: 14
   > contract address:    0x598535260F85fE7E5DdB729c9a8248dF7f7FaC2e
   > account:             0x627306090abaB3A6e1400e9345bC60c78a8BEf57
   > balance:             2.852194506
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