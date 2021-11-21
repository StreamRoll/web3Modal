# Easy Web3Modal with React

#### Metamask and WalletConnect baked in:

- `npm install` or `yarn install`
- `npm start` or `yarn start`
- That's it!
- Add more [Providers](https://github.com/web3modal/web3modal#provider-options)
### Using with ethers

By default, ethers provider is by default. To use the connected provider, import `Web3Context` from the web3 directory present inside `src` directory.

```
import React, { useContext } from 'react';
import { Web3Context } from './web3';

const { account, provider } = useContext(Web3Context);
```

To initialize an ethers Contract object
```
const daiContract = new ethers.Contract(daiAddress, daiAbi, provider);
```

To connect a signer to the above Read-only contract
```
const signer = await provider.getSigner();
daiContract.connect(signer);
```

Or to initialize a Contract with signer
```
const daiWithSigner = new ethers.Contract(daiAddress, daiAbi, provider.getSigner());
```

For more details, please refer [`ethers` documentation](https://docs.ethers.io/v5/getting-started/).


### Using with web3

You can wrap the provider received from Web3Context with web3js and use it as below
```
import React, { useContext } from 'react';
import { Web3Context } from './web3';

const { account, provider } = useContext(Web3Context);
const web3 = new Web3(provider);
```
For more details, please refer [`web3js` documentation](https://web3js.readthedocs.io/en/v1.3.4/index.html)


## Related efforts

If you are looking for a full-suite of Ethereum dapp with Smart contracts and other features, please check out the below links:

- [create-eth-app](https://github.com/paulrberg/create-eth-app) by PaulRBerg
- [scaffold-eth](https://github.com/austintgriffith/scaffold-eth) by Austin Griffith
