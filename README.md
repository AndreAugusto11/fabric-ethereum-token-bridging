# Fabric-Ethereum Token Bridging

This is a Hyperledger Mentorship 2022 project. All the information can be accessed [here](https://wiki.hyperledger.org/display/INTERN/Fabric-Ethereum+token+bridging). This repository contains the deliverables of the project.

## Description
One of the key use cases of blockchain integration is asset bridging: in essence, "locking" an asset (typically, a native coin or token) in a smart contract on its authoritative ledger and making available corresponding, newly minted (wrapped/shadow/...) assets on another. By now, bridging is supported by quite mature solutions in the cryptoworld; however, the same is not true for "consortial" distributed ledger technologies. At the same time, such functionality can be expected to become an important requirement in the not too distant future: for instance, a central bank may choose to create a high performance, Hyperledger Fabric-based Central Bank Digital Currency (CBDC) ledger with a strongly controlled set of "smart contracts", but allow controlled "bridging out" of the currency to dedicated distributed ledgers of industrial/enterprise cooperations. Last year, a CBDC prototype with such functionality was created at the Dept. of Measurement and Information Systems of the Budapest University of Technology and Economics (BME), in a research project supported by the central bank of Hungary (MNB); our initial experience with a custom Hyperledger Cactus and TokenBridge based solution showed that this is a problem worth more targeted experimentation and systematic R&D.

The proposed project consists of the following major activities:

* Analysing the implementation approaches of standard "token models" (ERC20, ERC-721, ... - as far as this has been already done) in native Fabric chaincode and creating conceptual mappings between standard Ethereum token types and Fabric-native assets (including, but not limited to, the different authentication and authorization approaches).
* Creating a brief review of the bridging approaches and mature technologies widely used in the cryptoworld.
* Performing a requirement analysis for bridging assets from Fabric to Ethereum-based networks (and back), taking into account that the parties performing the bridging have to be explicitly given permission to do so by an authority and may be subject to regulatory requirements (the simplest aspect of which is enforcing, or at least proving compliance to, an "allow list" of addresses on the Ethereum side during transactions).
* Based on the available open-source components, designing and prototyping a Fabric-Ethereum bridge fulfilling the requirements.

## Solution

The solution is available in Hyperledger Cactus as a Pull Request: [PR 2185](https://github.com/hyperledger/cactus/pull/2185).