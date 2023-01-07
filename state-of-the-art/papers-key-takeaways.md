
# Table of Contents
- [Table of Contents](#table-of-contents)
  - [Papers: Bridging Solutions](#papers-bridging-solutions)
    - [Bridges between islands: Cross-chain technology for distributed ledger technology](#bridges-between-islands-cross-chain-technology-for-distributed-ledger-technology)
    - [Bridging Sapling: Private Cross-chain Transfers](#bridging-sapling-private-cross-chain-transfers)
    - [Horizon: A Gas-Efficient, Trustless Bridge for Cross-Chain Transactions](#horizon-a-gas-efficient-trustless-bridge-for-cross-chain-transactions)
    - [A notary group-based cross-chain mechanism](#a-notary-group-based-cross-chain-mechanism)
    - [An Electricity Cross-Chain Platform based on Sidechain Relay](#an-electricity-cross-chain-platform-based-on-sidechain-relay)
    - [Trustless, privacy-preserving blockchain bridges](#trustless-privacy-preserving-blockchain-bridges)
    - [The Flexible Interledger Bridge Design](#the-flexible-interledger-bridge-design)
    - [Research on Cross-chain Technology of Blockchain: Challenges and Prospects](#research-on-cross-chain-technology-of-blockchain-challenges-and-prospects)
    - [Hermes: Fault-tolerant middleware for blockchain interoperability](#hermes-fault-tolerant-middleware-for-blockchain-interoperability)
    - [Enabling Enterprise Blockchain Interoperability with Trusted Data Transfer (industry track)](#enabling-enterprise-blockchain-interoperability-with-trusted-data-transfer-industry-track)
  - [Papers: Consortium - EVM (or similar) bridges](#papers-consortium---evm-or-similar-bridges)
    - [Niji: Autonomous Payment Bridge between Bitcoin and Consortium Blockchain](#niji-autonomous-payment-bridge-between-bitcoin-and-consortium-blockchain)
    - [Comparison of Hyperledger Fabric and Ethereum Blockchain](#comparison-of-hyperledger-fabric-and-ethereum-blockchain)
    - [Performance Analysis of Blockchain based Smart Grids with Ethereum and Hyperledger Implementations](#performance-analysis-of-blockchain-based-smart-grids-with-ethereum-and-hyperledger-implementations)


## Papers: Bridging Solutions

### Bridges between islands: Cross-chain technology for distributed ledger technology
This paper does not represent a very good addition to the state of the art due to being outdated.
It makes a good comparison of cross-chain approaches but does not add much to the existing information.

### Bridging Sapling: Private Cross-chain Transfers
The authors propose ZCLAIM, a protocol that enables cross-chain transactions with some degree of privacy (that comes from the zk-SNARKs of ZCash).
The paper specifies the operations/functions performed by every actor which is a very good starting point to understand the core functionality of a cross-chain bridge solution.

- Privacy: the protocol intends to have the same privacy level as Zcash. This protocol is subject to inference attacks, where entities (vaults) can guess the identity of the users by mapping lock and release transactions.

- Fault Tolerance: there is no reference to being a fault tolerant protocol.

- Auditability & Logging/Support/Alerting: there is no information regarding both logging procedures and alerting mechanisms. This is also related to auditability procedures, which are not possible to conduct under this circumstances.

### Horizon: A Gas-Efficient, Trustless Bridge for Cross-Chain Transactions
This new model is very interesting, where a relay has the responsibility of syncing one smart contract in one chain, with the headers from the other one (like an SPV client). The authors base the threat model of the protocol on rational adversaries, in which an entity misbehaves only if it benefits from it. Apart from this, the protocol is byzantine behavior resistance. Atomicity is guaranteed, but only assuming there is a Trusted Third party that acts in the client's interest by financial insuring the assets.

- Privacy: the protocol is design to work on a permissionless setting without concerns regarding the privacy levels offered to the clients.

- Fault Tolerance: the authors assume that a pool of relays and full nodes is always available to replace the ones that crash, but the procedure to do so is not specified, nor the way to detect faults.

- Auditability & Logging/Support/Alerting: there is no information regarding both logging procedures and alerting mechanisms. This is also related to auditability procedures, which are not possible to conduct under this circumstances.

### A notary group-based cross-chain mechanism
Instead of risking DoS attacks, or having a single point of failure by having a singe notary entity that mediates transactions between blockchains, there is a decentralization of this intermediary by deploying a network of notaries with incentive mechanisms for security purposes. This is a very good approach to defend ourselves from the aforementioned attacks, going towards a more decentralized solution.

- Privacy: every notary needs to have access to each ledger in which the actions will be performed. In a permissioned environment the notary needs to have the necessary permission to read/write from the ledger(s).

- Fault Tolerance: the authors base the protocol in an incentive mechanism to encourage nodes to maintain the network. Participants might get slashed for bad behavior, or have their reputation decreased if there are crashes or network partitions.

- Auditability & Logging/Support/Alerting: there is no information regarding both logging procedures and alerting mechanisms. This is also related to auditability procedures, which are not possible to conduct under this circumstances.

### An Electricity Cross-Chain Platform based on Sidechain Relay
The authors compare the proposed solution to Polkadot and Cosmos, having their own cross-chain communication protocol like IBC in Cosmos, or XCMP in Polkadot. It is not much clear what are the improvements to this existing solutions. Additionally, the main chain in this system completely acts as the bottleneck in the network, where the maximum throughput is achieved when 18 blockchains are connected, which are far away from the numbers provided (and expected in the future) for both Polkadot and Cosmos.

- Privacy: the authors mention a binding procedure between the public key of the clients to the authenticated identity information, but do not mention if it can be easily discovered by other sidechains, or parties in the network.

- Fault Tolerance: there is no reference to being a fault tolerant protocol.

- Auditability & Logging/Support/Alerting: there is no information regarding both logging procedures and alerting mechanisms. This is also related to auditability procedures, which are not possible to conduct under this circumstances.

### Trustless, privacy-preserving blockchain bridges
Presents the concept of coin mixer, which is a system that makes difficult to map deposits to withdrawals.
The main proposal is a trustless bridge based on sk-SNARKs, but it requires access to both ledgers to perform the operations, thus making it not suitable for permissioned blockchains.
Similarly as other solutions presented here, both sides of the protocol require light clients of each other's networks such that it is possible to verify proofs of transactions of the actual state of the blockchains.

- Privacy: the solution was built with privacy as the main concern. It uses the combination of a mixer (to shuffle deposits and withdrawals), light clients, and zero-knowledge proofs.

- Fault Tolerance: the protocol leverages an incentive mechanism to encourage nodes to maintain the network

- Auditability & Logging/Support/Alerting: there is no information regarding both logging procedures and alerting mechanisms. This is also related to auditability procedures, which are not possible to conduct under this circumstances.

### The Flexible Interledger Bridge Design
The proposed design is based on a trusted relay that interconnect different blockchains through pluggable ledger adaptors. This architecture is very similar to what Hyperledger Cactus offers, but following an event-driven design.
The overall protocol is completely agnostic to the underlying technologies and blockchains, which makes it suitable to perform cross-chain transactions within permissioned networks.

- Privacy: the presented protocol is intended to be as much transparent as possible, thus, no privacy concerns/measures are taken into consideration.

- Fault Tolerance: there is no reference to being a fault tolerant protocol.

- Auditability & Logging/Support/Alerting: there is no information regarding both logging procedures and alerting mechanisms. This is also related to auditability procedures, which are not possible to conduct under this circumstances.

### Research on Cross-chain Technology of Blockchain: Challenges and Prospects
This paper does not bring anything new to the table. It is focused on an analysis of the current solutions to achieve interoperability, but they were already mentioned before.


### Hermes: Fault-tolerant middleware for blockchain interoperability
Presents Hermes, an interoperability solution based on gateways and on the Open Digital Asset Protocol (ODAP). Hermes can be used in any blockchain that supports scripting capabilities (in order to lock and unlock assets through smart contract calls). This paper presents a novel approach to the problem by using gateways as relays between blockchain systems. Additionally, the protocol is suitable for both public and private environments.

- Privacy: the presented protocol is intended to be flexible regarding different legal frameworks, supporting different privacy requirements. The protocol is intended to be as agnostic as possible regarding the underlying DLTs, however, each gateway needs to have access and read/write permission to the underlying blockchains.

- Fault Tolerance: there is presented a sub-protocol to be triggered in case of a gateway crash. Additionally, the authors propose a rollback procedure to guarantee atomicity and finality.

- Auditability & Logging/Support/Alerting: by specifying the recovery procedure based on log generation and storage, the entire protocol is auditable by consulting Logs stored in the decentralized log storage (such as an IPFS network).

### Enabling Enterprise Blockchain Interoperability with Trusted Data Transfer (industry track)
The authors propose a solution architecture based on relay services based on different networks, that communicate with each other to exchange data and information. This architecture is similar to Hermes (last paper). Business logic and network rules are enforced through the deployment of smart contracts in each network. The authors evaluate the solution in respect to availability, confidentiality, and integrity. Additionally, the architecture is easily extensible by making small API modifications to the relay service so as to being compatible with other platform-specific implementations.

- Privacy: The same as the previous paper. the architecture is intended to be as agnostic as possible regarding the underlying networks, however, each relay service needs to have access and read/write permission to the underlying platform. The interaction between parties in different networks should be kept private and confidential.

- Fault Tolerance: there is no reference to being a fault tolerant protocol.

- Auditability & Logging/Support/Alerting: there is no information regarding both logging procedures and alerting mechanisms. This is also related to auditability procedures, which are not possible to conduct under this circumstances.

## Papers: Consortium - EVM (or similar) bridges

### Niji: Autonomous Payment Bridge between Bitcoin and Consortium Blockchain
According to the authors, previous solutions that do not use a trusted third party to mediate a cross-blockchain transfer require constantly monitoring of the blockchains. This paper proposes an solution based on an unidirectional Bitcoin payment channel on the consortium chain. A certain type of service is provided by the consortium chain, which is paid in Bitcoin through a payment channel.
This is a new approach to the problem, where there is no use of SPVs, which need to be constantly monitoring the networks for changes.

### Comparison of Hyperledger Fabric and Ethereum Blockchain
The paper explains and analyzes both systems regarding some metrics: usage, consensus, smart contracts, and performance. It does not provide bridging solutions analysis.

### Performance Analysis of Blockchain based Smart Grids with Ethereum and Hyperledger Implementations
The authors propose an architecture and implementation for both Ethereum and Hyperledger Fabric separately. There is no integration between both platforms that suites our needs.
