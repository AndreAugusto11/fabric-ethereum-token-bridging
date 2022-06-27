
# Report on Asset Representation Solutions

- [Report on Asset Representation Solutions](#report-on-asset-representation-solutions)
  - [Motivation](#motivation)
  - [Research Questions](#research-questions)
  - [Ethereum Token Standards](#ethereum-token-standards)
    - [ERC-20](#erc-20)
    - [ERC-721](#erc-721)
  - [Asset Representations In Hyperledger Fabric](#asset-representations-in-hyperledger-fabric)
    - [Hyperledger Fabric Token SDK](#hyperledger-fabric-token-sdk)
    - [Ethereum Standards chaincode implementation](#ethereum-standards-chaincode-implementation)
<br></br>

## Motivation
Our work explores existing token bridging solutions, which encompasses two phases. The first one concerns the protocol used to make the bridge between both parties. The second one is related to the translation of assets from one party to another (or their value). Our goal is to perform a bridge between Hyperledger Fabric and Ethereum, thus, it is also important to study how can we represent Ethereum tokens in Hyperledger Fabric, and the other way around.
Note: when talking about tokens, these can be defined as abstractions of any kind of business assets in the blockchain context.
<br></br>

## Research Questions
* How are assets represented in Ethereum blockchain?
* How are assets represented in Hyperledger Fabric?
* Are there mappings between Hyperledger Fabric and Ethereum blockchains?
<br></br>

## Ethereum Token Standards
Ethereum token standards appeared as a way of standardizing token representation through the implementation of smart contracts. This way, every system is interoperable with each other by implementing the same standard.

### ERC-20
ERC-20 was the first standard introduced with regards to Fungible Tokens. Fungible tokens are interchangeable, which means that one token is equal to any other token (one dollar is always one dollar; one vote is always one vote...).

**Available Features (Smart Contract Methods)**
- name()
- symbols()
- decimals()
- totalSupply()
- balanceOf(address)
- transfer(to, value)
- transferFrom(from, to, value)
- approve(spender, value)
- allowance(owner, spender)
...

Other methods can be implemented to realize custom behavior in the smart contract.

### ERC-721
ERC-721 was the first standard introduced with regards to Non-Fungible Tokens. Non-Fungible tokens are not interchangeable, which means that one token is unique (one painting is always unique, even if we make a replica it will not be exactly the same).

**Available Features (Smart Contract Methods)**
- transfer()
- approval()
- approvalForAll()
- balanceOf(address)
- ownerOf(tokenID)
- transferFrom(from, to, tokenID)
- approve(address, tokenID)
...

Notice the main difference between both interfaces is the use of TokenIds instead of value given the uniqueness of these tokens.

## Asset Representations In Hyperledger Fabric

There are multiple solutions to realize the representation of assets in Hyperledger Cactus. We, therefore, analyze some solution in this section.

### Hyperledger Fabric Token SDK
TBD

### Ethereum Standards chaincode implementation
At the moment we can find multiple chaincode implementations of ERC20 and ERC721 token standards, which offer exactly the same functionality as these ones, but are designed to work on Fabric networks.

One example is ERC20-Token-On-Hyperledger repository (https://github.com/grepruby/ERC20-Token-On-Hyperledger), however this is not an official Hyperledger Foundation project (even though it has 36 stars and 22 forks).
