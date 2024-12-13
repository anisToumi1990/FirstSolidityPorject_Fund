## Foundry Project : Fund ME

# Thank you!
**⭐️ Thank you Patrick Collins and Cyfrin Updraft! ⭐️**

I would like to extend my sincere gratitude to Patrick Collins, the creator of the course, and Cyfrin Updraft, the platform hosting it. This course has been instrumental in my understanding of Solidity and smart contract development. Thanks to the lessons and guidance provided, I was able to successfully build and deploy my first project. 
Your efforts have made learning enjoyable and practical, and I am excited to continue my blockchain development journey!


- [Thank you!](#thank-you)
- [Usage](#usage)
  - [Deploy](#deploy)
  - [Testing](#testing)
    - [Test Coverage](#test-coverage)
- [Deployment to a testnet or mainnet](#deployment-to-a-testnet-or-mainnet)
  - [Scripts](#scripts)
    - [Withdraw](#withdraw)
  - [Estimate gas](#estimate-gas)
- [Formatting](#formatting)
- [About me](#about-me)


# Usage

## Deploy

```shell
$ forge script script/DeployFundMe.s.sol
```

## Testing


```shell
$ forge test
```

or 

```shell
// Only run test functions matching the specified regex pattern.

$ forge test --match-test testFunctionName
```

or

```shell
$ forge test --fork-url $SEPOLIA_RPC_URL
```

### Test Coverage

```shell
$ forge coverage
```

# Deployment to a testnet or mainnet

1. Setup environment variables

You'll want to set your `SEPOLIA_RPC_URL` and `PRIVATE_KEY` as environment variables. You can add them to a `.env` file.

- `PRIVATE_KEY`: The private key of your account (like from [metamask](https://metamask.io/)). **NOTE:** FOR DEVELOPMENT, PLEASE USE A KEY THAT DOESN'T HAVE ANY REAL FUNDS ASSOCIATED WITH IT.
  - You can [learn how to export it here](https://metamask.zendesk.com/hc/en-us/articles/360015289632-How-to-Export-an-Account-Private-Key).
- `SEPOLIA_RPC_URL`: This is url of the sepolia testnet node you're working with. You can get setup with one for free from [Alchemy](https://alchemy.com/?a=673c802981)

Optionally, add your `ETHERSCAN_API_KEY` if you want to verify your contract on [Etherscan](https://etherscan.io/).

2. Get testnet ETH

Head over to [faucets.chain.link](https://faucets.chain.link/) and get some testnet ETH. You should see the ETH show up in your metamask.

3. Deploy

```shell
$ forge script script/DeployFundMe.s.sol --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast --verify --etherscan-api-key $ETHERSCAN_API_KEY
```

## Scripts

After deploying to a testnet or local net, you can run the scripts. 

Using cast deployed locally example: 

```shell
$ cast send <FUNDME_CONTRACT_ADDRESS> "fund()" --value 0.1ether --private-key <PRIVATE_KEY>
```

or
```shell
$ forge script script/Interactions.s.sol:FundFundMe --rpc-url sepolia  --private-key $PRIVATE_KEY  --broadcast
$ forge script script/Interactions.s.sol:WithdrawFundMe --rpc-url sepolia  --private-key $PRIVATE_KEY  --broadcast
```

### Withdraw

```shell
$ cast send <FUNDME_CONTRACT_ADDRESS> "withdraw()"  --private-key <PRIVATE_KEY>
```

## Estimate gas

You can estimate how much gas things cost by running:

```shell
$ forge snapshot
```

And you'll see an output file called `.gas-snapshot`


# Formatting

To run code formatting:
```shell
$ forge fmt
```






# About me

[![Anis Toumi Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/Anis_NFT)
[![Anis Toumi Linkedin](https://img.shields.io/badge/Linkedin-0e76a8?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/anis-toumi-1b158a83)