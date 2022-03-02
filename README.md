# Decentralized Supply chain application

This repo contains code related to supply chain DApp to show different actions taken in a typical supply chain application. There are four main roles in the workflow of the porject 1. Farmer, 2. Distributor 3. Retailer and 4. Consumer. Below are the actions for each role:
1. Farmer:
Harvest --> Process --> Pack --> ForSale
2. Distributor:
Buy --> Ship
3. Retailer:
Receive
5. Consumer
Purchase

### Contracts on Rinkeby:
1. FarmerRole:\
    Contract Address: 0xf83B374A0AA3B8e01FBa1BA8e6388A9bB661EF7A\
    Transaction hash: 0x7b40db96d87997241de863f2a8818a4ebc3544c2f2c909a65a3b47e968c829dd
2. DistributorRole:\
    Contract Address: 0x85B8E582B00A4d390FC6C6BB0ec5dC1F006c8441\
    Transaction hash: 0x147766524e0368ec9a0485ee3e31e385141380f6a3ba9be8a0a4833196eca090
3. RetailerRole:\
    Contract Address: 0x6413f302ec142b6ec13C2042f4bb22C62b78D108\
    Transaction hash: 0xbae028585544161d5a6c6d51db9b2712de12c337bf861898f3a849620081292f
4. ConsumerRole:\
    Contract Address: 0x6391555b3701B31772891510b19464345e34F98e\
    Transaction hash: 0x3af1163f16e6be66748c32942e7df5369b5888c5c890a022560b81ed0d0eceed
5. SupplyChain:\
    Contract Address: 0xD7D21b7eCcb328d907CA4B7088D11b8819f46A6C\
    Transaction hash: 0x2e95b58895e1d0f4da5c3fff3781a9f8518d93cfcce004dd2cc31b59806a6f65

### High level design representation of the workflow:

#### Activity Diagram:
![activity diagram](images/activity.drawio.png)

#### State Diagram:
![state diagram](images/state.drawio.png)

#### Sequence Diagram:
![sequence diagram](images/sequence.drawio.png)

#### Class Diagram:
![class diagram](images/class.drawio.png)

### Libraries used the project:
1. Node.js
2. NPM: Node Package Manager
3. Truffle: Development framework for Ethereum
4. Ganache: For test accounts to be used on ethereum
5. webpack-dev-server: For running node website on localhost
6. IPFS - For hosting website on blockchain
7. MetaMask extension in your browser

### Running the application

Change directory to ```supplychain-dapp``` folder and install all requisite npm packages (as listed in ```package.json```):
```
cd supplychain-dapp
npm install
```
Compile smart contract:

```
truffle compile
```
Migrate smart contracts to the locally running blockchain, ganache-cli:

```
truffle migrate
```
If deploying on rinkeby - use truffle migrate --reset --network rinkeby

```
truffle test
```

All 10 tests should pass.

![truffle test](images/test-pass.png)

Launch the front-end for the DApp from a separate terminal window:

```
npm run dev
```
Push front-end site on to IPFS either using IPFS Desktop or IPFS cli
```
npm install --save ipfs-api
npm install --save-dev brfs
ipfs.exe add -r supplychain-dapp
//To publish pin
ipfs.exe name publish <<hashid of supplychain-dapp folder>>
```

IPFS Site: https://ipfs.io/ipfs/Qmbx7Ymn63PPHE5MggGwowy3Q61s1HDwhZWpAJym3PDRab/
If you get gateway timeout accessing the IPFS site, make sure atleast one node is serving your content by executing: 
```
ipfs.exe dht findprovs Qmbx7Ymn63PPHE5MggGwowy3Q61s1HDwhZWpAJym3PDRab
```
