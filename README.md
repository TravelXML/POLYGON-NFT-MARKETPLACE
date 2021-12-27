# NFT Marketplace Built With Polygon, Solidity, IPFS & Next.js

![Header](https://raw.githubusercontent.com/TravelXML/POLYGON-NFT-MARKETPLACE/main/NFT%20Marketplace.png)

[NFT Marketplace Built With Polygon, Solidity, IPFS & Next.js](https://github.com/TravelXML/POLYGON-NFT-MARKETPLACE)
## Objective

Create NFT Marketplace With Below Options.

* Home
* Sell Digital Asset
* My Digital Assets
* Creator Dashboad


### Run this project
#### How to setup locally?

To run this project locally, follow these steps.

#### 1. Clone the project locally, change into the directory, and install the dependencies:

```sh
git clone https://github.com/TravelXML/POLYGON-NFT-MARKETPLACE.git

cd POLYGON-NFT-MARKETPLACE

# install using NPM or Yarn
npm install

# or

yarn
```

#### 2. Start the local Hardhat node

```sh
npx hardhat node
```

#### 3. With the network running, deploy the contracts to the local network in a separate terminal window

```sh
npx hardhat run scripts/deploy.js --network localhost
```

#### 4. Start the app

```
npm run dev
```
![image](https://user-images.githubusercontent.com/8361967/147458787-c5e3f23c-58ce-4a63-910d-f6ca114ce587.png)

Navigate [http://localhost:3000](http://localhost:3000) on the browser you can see your marketplace is up.

Click on Sell Digital Asset

![image](https://user-images.githubusercontent.com/8361967/147459946-cc4742ee-2776-4083-a42f-c3975099325a.png)

Click on Home

![image](https://user-images.githubusercontent.com/8361967/147459625-fdcbcdb5-2e12-4806-b37b-c07f09128768.png)


### Configuration

To deploy to Polygon test or main networks, update the configurations located in __hardhat.config.js__ to use a private key and, optionally, deploy to a private RPC like Infura.

```javascript
require("@nomiclabs/hardhat-waffle");
const fs = require('fs');
const privateKey = fs.readFileSync(".secret").toString().trim() || "01234567890123456789";
const infuraId = fs.readFileSync(".infuraid").toString().trim() || "";

module.exports = {
  defaultNetwork: "hardhat",
  networks: {
    hardhat: {
      chainId: 1337
    },
    /*
    mumbai: {
      // Infura
      url: `https://polygon-mumbai.infura.io/v3/${infuraId}`
      //url: "https://rpc-mumbai.matic.today",
      accounts: [privateKey]
    },
    matic: {
      // Infura
      url: `https://polygon-mainnet.infura.io/v3/${infuraId}`,
      //url: "https://rpc-mainnet.maticvigil.com",
      accounts: [privateKey]
    }
    */
  },
  solidity: {
    version: "0.8.4",
    settings: {
      optimizer: {
        enabled: true,
        runs: 200
      }
    }
  }
};
```

If using Infura, update __.infuraid__ with your [Infura](https://infura.io/) project ID.
#### Deploy into Mumbai test network
Here, we will add the following configurations for the Mumbai test network as listed here:

* Network Name: Mumbai TestNet

* New RPC URL: https://rpc-mumbai.matic.today

* Chain ID: 80001

* Currency Symbol: Matic

Save this, then you should be able to switch to and use the new network!

Finally, you will need some testnet Matic tokens in order to interact with the applications.

To get these, you can visit the Matic Faucet, inputting the address of the wallets that you would like to request the tokens.
Deploying to the Matic / Polygon network

Now that you have some Matic tokens, you can deploy to the Polygon network!

To do so, be sure that the address associated with the private key you are deploying your contract with has received some Matic tokens in order to pay the gas fees for the transaction.

To deploy to Matic, run the following command:

    npx hardhat run scripts/deploy.js --network mumbai

Once the contracts have been deployed, you should be able to update the contract addresses in your project and test on the new network 🎉!

    npm run dev

Deploying to Mainnet

To deploy to the main Matic / Polygon network, you can use the same steps we set up for the Mumbai test network.

The main difference is that you'll need to use an endpoint for Matic as well as import the network into your MetaMask wallet as listed here.

An example update in your project to make this happen might look like this:
```javascript

/* hardhat.config.js */

/* adding Matic main network config to existing config */
...
matic: {
  url: "https://rpc-mainnet.maticvigil.com",
  accounts: [privateKey]
}
…
```

Public RPCs like the one listed above may have traffic or rate-limits depending on usage. You can sign up for a dedicated free RPC URL using services like Infura, MaticVigil, QuickNode, Chainstack, or Ankr.

For example, using something like Infura:

  url: `https://polygon-mainnet.infura.io/v3/${infuraId}`


After Deploying to Mumbai Test Network, you scan your address and see what all transactions occurred.
![image](https://user-images.githubusercontent.com/8361967/147469842-c916a347-89cf-40ff-a4eb-586420105801.png)





