# Implementation

This file provides an overview of the solution to be implemented in Hyperledger Cactus.

<p align="center">
  <img src="images/sequence-diagram.png" width="100%" />
</p>

### CBDC CC
This smart contract definition intends to specify the CBDC details. This implements ERC-20 (or similar) standard, which allows the implementation of fungible tokens like a stablecoin.

### ASSET REF CC
This smart contract definition intends to encapsulate a certain amount of a determined token in a new data structure. The new object has:
- **id**: ID so that the object can be referenced.
- **isLocked**: boolean indicating whether this object is locked or not.
- **tokens**: the number of tokens referenced in this object
- **typeOfTokens**: the type of tokens referenced in this object

This smart contract must support at least the splitting functionality:
- **split**: split one object into two where the sum of the total tokens involved is the same.

### ASSET REF SC
Not sure if this is necessary, because we could directly mint tokens in the EVM SC.

### EVM SC
Where the tokens will be minted in the target blockchain. This would have the same token definition as CBDC CC. 