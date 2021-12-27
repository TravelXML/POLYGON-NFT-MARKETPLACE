# NFT Marketplace Built With Polygon, Solidity, IPFS & Next.js

![Header](https://raw.githubusercontent.com/TravelXML/POLYGON-NFT-MARKETPLACE/main/NFT%20Marketplace.png)

## Objective

Create NFT Marketplace With Below Options.

> Home
> Sell Digital Asset
> My Digital Assets
> Creator Dashboad


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



