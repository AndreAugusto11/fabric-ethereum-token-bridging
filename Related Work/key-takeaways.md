
# Table of Contents
- [Table of Contents](#table-of-contents)
  - [Papers](#papers)
    - [Bridges between islands: Cross-chain technology for distributed ledger technology](#bridges-between-islands-cross-chain-technology-for-distributed-ledger-technology)
    - [Bridging Sapling: Private Cross-chain Transfers](#bridging-sapling-private-cross-chain-transfers)
    - [Horizon](#horizon)
    - [A notary group-based cross-chain mechanism](#a-notary-group-based-cross-chain-mechanism)
    - [An Electricity Cross-Chain Platform based on Sidechain Relay](#an-electricity-cross-chain-platform-based-on-sidechain-relay)
    - [Trustless, privacy-preserving blockchain bridges](#trustless-privacy-preserving-blockchain-bridges)
    - [The Flexible Interledger Bridge Design](#the-flexible-interledger-bridge-design)
    - [Research on Cross-chain Technology of Blockchain: Challenges and Prospects](#research-on-cross-chain-technology-of-blockchain-challenges-and-prospects)


## Papers

### Bridges between islands: Cross-chain technology for distributed ledger technology
This paper does not represent a very good addition to the state of the art due to being outdated.
It makes a good comparison of cross-chain approaches but does not add much to the existing information.

### Bridging Sapling: Private Cross-chain Transfers
The authors propose ZCLAIM, a protocol that enables cross-chain transactions with some degree of privacy (that comes from the zk-SNARK of ZCash).
The paper specifies the operations/functions performed by every actor which is a very good starting point to understand the core functionality of a cross-chain bridge solution.

### Horizon
This new model is very interesting, where a relay has the responsibility of syncing one smart contract in one chain, with the headers from the other one (like an SPV client). The authors base the threat model of the protocol on rational adversaries, in which an entity misbehaves only if it benefits from it. Apart from this, the protocol is byzantine behavior resistance. Atomicity is guaranteed, but only assuming there is a Trusted Third party that acts in the client's interest by financial insuring the assets.

### A notary group-based cross-chain mechanism
Instead of risking DoS attacks, or having a single point of failure by having a singe notary entity that mediates transactions between blockchains, there is a decentralization of this intermediary by deploying a network of notaries with incentive mechanisms for security purposes. This is a very good approach to defend ourselves from the aforementioned attacks, going towards a more decentralized solution.

### An Electricity Cross-Chain Platform based on Sidechain Relay
The authors compare the proposed solution to Polkadot and Cosmos, having their own cross-chain communication protocol like IBC in Cosmos, or XCMP in Polkadot. It is not much clear what are the improvements to this existing solutions. Additionally, the main chain in this system completely acts as the bottleneck in the network, where the maximum throughput is achieved when 18 blockchains are connected, which are far away from the numbers provided (and expected in the future) for both Polkadot and Cosmos.

### Trustless, privacy-preserving blockchain bridges
Presents the concept of coin mixer, which is a system that makes difficult to map deposits to withdrawals.
The main proposal is a trustless bridge based on sk-SNARKs, but it requires access to both ledgers to perform the operations, thus making it not suitable for permissioned blockchains.
Similarly as other solutions presented here, both sides of the protocol require light clients of each other's networks such that it is possible to verify proofs of transactions of the actual state of the blockchains.

### The Flexible Interledger Bridge Design
The proposed design is based on a trusted relay that interconnect different blockchains through pluggable ledger adaptors. This architecture is very similar to what Hyperledger Cactus offers, but following an event-driven design.
The overall protocol is completely agnostic to the underlying technologies and blockchains, which makes it suitable to perform cross-chain transactions within permissioned networks.

### Research on Cross-chain Technology of Blockchain: Challenges and Prospects
This paper does not bring anything new to the table. It is focused on an analysis of the current solutions to achieve interoperability, but they were already mentioned before.