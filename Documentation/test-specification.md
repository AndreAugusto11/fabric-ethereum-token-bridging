# Test Specification
This file intends to make the testing specification for our bridging application. We assume the following nomenclature:
- **ADDRESS 1**: Represents the bridging initiating party in the main ledger. It can be either the final user, a financial institution on behalf of the same, etc..
- **ADDRESS 2**: The address of the final user in the target ledger.

## Functional Tests
Let us define different scenarios:

1. **ADDRESS 1** escrows X CBDC in the main ledger, and those tokens cannot be moved by **ADDRESS 1**, or other party besides the escrow entity.

2. **ADDRESS 1** escrows X CBDC in the main ledger, and those tokens can be moved by the bridging entity.

3. **ADDRESS 1** initiates bridging out of X CBDC, and only X CBDC are minted to **ADDRESS 2**.

4. ADDRESS (where A != 1) initiates bridging out of X CBDC escrowed by **ADDRESS 1**, and bridging operation fails.

5. **ADDRESS 1** initiates bridging out of X CBDC, and **ADDRESS 2** has access to the X CBDC minted to **ADDRESS 2**.

6. **ADDRESS 1** initiates bridging out of X CBDC, and **ADDRESS B** (where B != 2) has not access to the X CBDC minted to **ADDRESS 2**.

7. **ADDRESS 2** initiates bridging back of X CBDC, and X CBDC are burnt in **ADDRESS 2**, and only X CBDC are unlocked back to **ADDRESS 1** in the main ledger.

8. **ADDRESS 2** initiates bridging back of Y CBDC (where Y < X), and Y CBDC are burnt in **ADDRESS 2**, and only Y CBDC are unlocked back to **ADDRESS 1**.

9. **ADDRESS B** (where B != 2) initiates bridging back of X CBDC owned by **ADDRESS 1**, and bridging operation fails.

10. **ADDRESS A** (where A != 2) initiates bridging back of X CBDC owned by **ADDRESS 1**, and bridging fails.

## Non-Functional Tests
We assume the same nomenclature as before. Let us define different scenarios:

1. **ADDRESS 1** initiates bridging out of X CBDC and Gateway 1 fails (should we specify where in the protocol that happens?) and recovers before timeout. The escrow should be in control of the X CBDC in the main ledger, and X CBDC should be minted to **ADDRESS 2**.

2. **ADDRESS 1** initiates bridging out of X CBDC and Gateway 1 fails (should we specify where in the protocol that happens?) and does not recover before timeout. **ADDRESS 1** should be in control of the X CBDC and the nothing should be minted to **ADDRESS 2**.