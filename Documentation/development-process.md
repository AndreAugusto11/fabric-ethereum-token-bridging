
This file provides an overview of the development process to be followed, assuming the implementation is being performed in Hyperledger Cactus, using the implementation of the ODAP plugin.

### Steps to bridge-out tokens from CBDC ledger to EVM compatible ledger (we assume Fabric and Besu)

1. Creation of a package to realize the bridge between Hyperledger Fabric and EVM based DLTs.
2. Creation of a Hyperledger Fabric network with the default configuration of 2 organizations, 1 peer in each, 1 orderer, 1 CA (we can possibly extend this to make a more complex use-case in the future).
3. Creation of a Hyperledger Besu network and the set up one account (to which the assets/tokens will be minted)
4. Set up connections to Hyperledger Fabric and Hyperledger Besu networks.
5. (Possibly integrate the Fabric Token SDK project, and work with the asset/token representation solutions)
6. Implementation of common asset/token definition that both ledgers' SC will implement/extend (so as to create a common understanding between them).
7. Chaincode implementation for token locking.
8. Smart Contract implementation for asset/token minting in Hyperledger Besu.
9. Package implementation to realize the bridge-out of Fabric tokens to a Hyperledger Besu network.
<br></br>

<p align="center">
  <img src="images/dev-process.png" width="100%" />
</p>


### What is it done already?
- Creation, set up, and integration of both Hyperledger Fabric and Hyperledger Besu.
- ODAP plugin to realize the bridge between both blockchains.

### What is to be done?
- Creation of a package to implement Fabric - EVM compatible ledger bridge.
- Common smart contract definition.
- Implementation of specific smart contracts for each side.