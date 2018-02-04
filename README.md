---
NEO-PY
---

# Table of Contents
  * [Purpose](#chapter-0)
  * [NEO Development](#chapter-10)
  * [NEO Documentation Summary](#chapter-1000)
  * [NEO References](#chapter-1100)

## Purpose <a id="chapter-0"></a>

Learning about the NEO blockchain by summarising their documentation and following their Python development guides

## NEO Development <a id="chapter-10"></a>

### NEO Smart Contracts

* Smart Contracts
  * Definition - Agreement by contract participants to fulfill a digital commitment. They are deployed on a decentralised and immutable blockchain to improve the efficiency of traditional social structure.

* NEO Smart Contract 2.0
  * Contract Types
    * Validation Contracts
    * Function Contracts
    * Application Contracts
  * Communication
    * Smart Contract is executed in the NeoVM and uses the Interactive Service Layer to communicates with the outside
  * Upgrades
    * API of the Interactive Service Layer may be used to Upgrade the Smart Contract Function

* NEO Python **neo-python**
  * Definition
    * Python-based P2P Node and SDK for the NEO blockchain
    * Interactive CLI to Configure/Inspect the Node
    * NEO Smart Contracts (in `.avm` format)
      * Compiling, Testing, Deploying, and Running
      * Event Monitoring with `Runtime.Log` and `Runtime.Notify`
    * Wallet functionality is NEP2 (Passphrase-protected private key) and NEP5 (Token Standard) Compliant
    * RPC Client

### [NEO Nodes (Private Chains) and API/SDK Interaction](http://docs.neo.org/en-us/node/introduction.html)

* **Full-Nodes** store the whole blockchain and are connected to it through a P2P network. All nodes in the blockchain network are equal and act both as Client Interface and Server. Nodes API may be accessed via [Ports](http://docs.neo.org/en-us/node/introduction.html#port-description). [Comparison of Neo-GUI and Neo-CLI](http://docs.neo.org/en-us/node/introduction.html#comparison-of-gui-node-and-cli-node-functions).
  * **Programs**
    * **Neo-GUI** is a GUI intended for Neo Users
    * **Neo-CLI** provides External API for basic Wallet functions, helps other Nodes reach Consensus in the Network to generate New Blocks, and is intended for NEO Developers.
      * Note: [NEO Network Protocol](http://docs.neo.org/en-us/node/network-protocol.html#network-message) will provide a Low-level API for transaction types not currently supported by Neo-CLI (i.e. claiming GAS, sending NEO without an open Wallet).

* TODO - In Progress

## NEO Documentation Summary <a id="chapter-1000"></a>

* [X] - [NEO White Paper](http://docs.neo.org/en-us/index.html)
  * Digital Asset Types with NEO
    * Global Assets - recorded in system space and identifiable by all smart contracts and clients
    * Contract Assets - recorded in the private storage area of a smart contract, may adhere to certain standards, and require a compatible client to be recognised
  * [X] - Digital Identity
    * Digital Identity Definition - Electronic identity of entities
    * Digital Identity with NEO
      * Goal - Implement set of X.509 compatible Digital Identity Standards
      * Support for Digital Identity System Standard - based on PKI (Public Key Infrastructure) X.509 standard
      * Support for Certificate Issuance Models - compatible X.509 level and Web of Trust Point-to-point 
      * Supports Verification of Identity - facial features, fingerprint, voice, sms, other multi-factor authentication methods
      * Replace Online Certificate Status Protocol (OCSP) with blockchain to manage and record X.509 Certificate Revocation List (CRL)
  * [X] - Smart Contracts
    * NeoContract - independent Smart Contract System for smart contract development, debugging, and compilation that uses the NeoVM
  * [X] - Application
    * Node Program - full node and light node programs, mobile web clients that do not need to synchronise with the blockchain, hardware wallet
    * Blockchain Explorer
    * SDK Development Kit - i.e. Python, Go, JavaScript (future), etc
    * Smart Contract Compiler and IDE Plugin - i.e. JavaScript, Python, Ruby, Go, etc
    * Decentralised Apps (DApps)
      * Smart funds, AI-agent assisted legal smart contracts, social networking, automated tokens liquidity providers, decentralised exchange (DEX), secure communication protocol, data exchange market, intellectual property trading market, prediction market, advertising market, hashpower market, NeoGas market

  * [X] - Ecosystem
    * Open Source Community - to achieve the goal of providing an intelligent economic network it provides:
      * Development Tools (mature)
      * Development Docs (improving)
      * Education and Training Activities (organised)
      * Financial Support
        * Reward User Experience (UX) Design Improvements

  * [X] - Management Model of NEO
    * Economic Model
      * Native Tokens
        * NEO (NEO) - 100 Million tokens (minimum unit is 1) generated at Genesis block, represents the right to manage the network (voting for bookkeeping, changing network parameters)
        * NeoGas (GAS) - 100 Million tokens (minimum unit is 0.00000001) generated using a decay algorithm to encourage the holding of NEO and represents a fuel token used to realise network resource control, and creating economic incentives for bookkeepers and to prevent abuse of resources, since the NEO network charges for operation and storage of tokens and smart contracts
      * NeoID - used to prioritise transactions and smart contracts with qualified identities during spam transactions, whereas priority in smart contract transactions may also be obtained by paying GAS for users without a qualifying digital identity
    * Distribution Mechanism
      * NEO Distribution
        * 50% of the tokens are managed by NEO Council to support NEO long-term development, operation and maintenance and are unlocked after 16th Oct 2017 and will not enter exchanges.
          * 10% of these tokens used to motivate NEO developers and NEO Council members
          * 10% of these tokens used to motivate developers in the NEO ecosystem
          * 15% of these tokens used to cross-invest in other blockchain NEO Projects owned by NEO Council 
          * 15% of these tokens retained as Contingency
          * Note: Annual use of NEO to not exceed 15%
      * GAS Distribution
        * GAS is generated with each New Block (100 Million released over the next ~22 years until the 44 Millionth block)
          * Year 1 - 16% o the GAS created, at rate of 8 GAS per block, given block interval of ~15-20 sec and 2 Million blocks generated
          * Year 2 - reduced rate of 7 GAS per block (i.e. after 2 Million blocks generated)
          * Year N - reduced rate of (8 - (N - 1)) GAS per block
        * GAS has an Initial Total Amount of 0
        * GAS distributed proportionally according to NEO holding ratio of an address that may be claimed any time
    * Governance Mechanism
      * On-Chain Governanece - NEO token holders are network owners, managing the network through voting and using GAS (generated from NEO) to utilise network functions
      * Off-Chain Governance - NEO Council comprises founding members, management and technical committees, and secretariat, who are responsible for Strategic and Technical Decision-Making, and responsible to the NEO Community for NEO Ecosystem promotion and development

  * [X] - NEO Technology Implementation
    * **dBFT** Consensus Mechanism is Delegate Byzantine Fault Tolerant (dBFT)
      * Definition - BFT consensus mechanism enabling participation in consensus through proxy voting at large scale in the network and continues in real-time without a fixed-term 
      * Process - 
        * Voting for Bookkepers by NEO token holders voting for those they support
        * Selected Bookkeepers reach consensus and generate New Blocks using a BFT algorithm
      * Security and Availability
        * Fault Tolerance - `f = (n - 1) / 3` for Consensus System with `n` Consensus Nodes
          * Resistant - resistant to general Byzantine failures and suitable for any network environment
          * Finality - prevents transactions from being revoked or rolled back after confirmations are finalised in a block
      * Performance
        * Throughput (Actual) - up to 1,000 TPS (transactions per second)
        * Throughput (Potential) - up to 10,000 TPS, through Optimisation
      * Digital Identity
        * Compliant financial assets may be registered on the NEO network
        * Individuals or institutional bookkeeper smay use their real name
        * Judicial decisions may freeze, revoke, inherit, retrieve, or transfer ownership
    * **NeoContract** Smart Contract System
      * **NeoVM** Universal Blockchain Virtual Machine
        * Lightweight VM (similar to JVM and .NET runtime) with virtual CPU that is suitable for reading/executing smart contract instructions sequentially, and may be ported to non-blockchain systems, and extended with a JIT (real-time compiler) mechanism
        * [NeoVM System Architecture](http://docs.neo.org/en-us/sc/tutorial.html#neovm)

        ![alt text](http://docs.neo.org/assets/neo-vm.jpg "NeoVM System Architecture Diagram")

      * **InteropService** Interoperable Services
        * Service VMs that load the blockchain ledger, digital assets, digital identity, persistent storage area, NeoFS (similar to IPFS), and other services
        * Service VMs may be accessed by Smart Contracts at runtime
        * Low-Coupling Design allows NeoVM to be ported and used with any blockchain or non-blockchain system to increase Smart Contract utility
      * **DevPack** High-level Language Compiler and IDE Plugin
        * DevPack Compilers can compile Smart Contracts written in Java/Kotlin and C# into NeoVM instructions using fimiliar IDEs
        * Static Analyis may be used to create a Smart Contract Call Tree that the NEO Node may dynamically fragment to achieve expansion and overcome the "jamming effect" of blockchain systems
    * **NeoX** Cross-Chain Interoperability Agreement (Protocol)
      * Definition - NeoX is a Protocol that implements Cross-Chain Interoperability and makes Cross-Chain Collaborations and Cross-Chain Smart Contract Applications possible as it allows for Cross-Chain Smart Contracts to perform different parts across multiple chains and either succeeding or reverting as a whole. Similar concept to Polkadot.
      * **Cross-Chain Assets Exchange Agreement**
        * **NeoContract** function used to create a Contract Account for each Participant.
        * **NeoX** allows Multiple Participants to exchange assets across different chains, where Multiple Steps of a Transaction succeed or fail together
        * **NeoX** allows other blockchains to Participate through being compatible with **NeoContract** and providing simple Smart Contract functionality
      * **Cross-Chain Distributed Transaction Protocol**
        * **Cross-Chain Distributed Transactions** mean Multiple Steps of a Transaction are scattered across different blockchains with transaction consistency
    * **NeoFS** Distributed Storage Protocol
      * Definition
        * NeoFS is an InteropService of the NeoContract system that enables Smart Contracts to store large files on the blockchain and set file access privileges.
        * NeoFS may be combined with Digital Identity for assigning, sending, and revoking Digital Certificates without a central server.
        * NeoFS may store Old Block Data instead of on Full Nodes in future to increase scalability 
        * NeoFS uses Distributed Hash Table (DHT) technology by indexing data through file content (Hash) and dividing large files into fixed-size data blocks that are distributed and stored across different NEO Nodes.
      * Redundancy and Reliability Trade-off
        * Token incentives
        * Backbone Nodes - provide services for files with user-defined requirements of Stability and High Reliability
        * Other Nodes - files with user-defined Low Reliability requirements may be stored and accessed almost for free
    * **NeoQS** (Quantum Safe) Anti-Quantum Cryptography Mechanism
      * Definition - Lattice-based cryptographic mechanism intended to stop the NEO blockchain from being compromised by quantum computers

* [X] - [Neo Smart Contracts 2.0](http://docs.neo.org/en-us/sc/introduction.html)
  * Contract Types
    * Validation Contracts
    * Function Contracts
    * Application Contracts
  * Features
    * Certainty
    * High Performance
      * NeoVM (NEO Universal Lightweight Virual Machine) used as a contract execution environment
    * Expandability
      * High Concurrency, Dynamic Partitioning, Low-Coupling Contract Procedure Design (executed in NeoVM and communicates through the Interactive Service Layer API to allow upgrading of the smart contract function)
  * Developer Benefits
    * Compilers and Plug-ins for: Python, JavaScript (future), etc
    * Debugging at NeoVM level
    * TestNet GAS provided for development

* [X] - [NeoContract White Paper](http://docs.neo.org/en-us/index.html)
* [ ] - [NEO Enhancement Proposals (NEP)](https://github.com/neo-project/proposals)

## NEO References <a id="chapter-1100"></a>

* [City Of Zion](https://github.com/CityOfZion)