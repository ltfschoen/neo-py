
---
NEO-PY
---

# Table of Contents
  * [Purpose](#chapter-0)


## Purpose <a id="chapter-0"></a>

## References <a id="chapter-1000"></a>

* [ ] - [NEO White Paper](http://docs.neo.org/en-us/index.html)
  * Digital Asset Types with NEO
    * Global Assets - recorded in system space and identifiable by all smart contracts and clients
    * Contract Assets - recorded in the private storage area of a smart contract, may adhere to certain standards, and require a compatible client to be recognised
  * [ ] - Digital Identity
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

  * [ ] - NEO Technology Implementation
    * Consensus Mechanism is Delegate Byzantine Fault Tolerant (dBFT)
      * dBFT
        * Definition - BFT consensus mechanism enabling participation in consensus through proxy voting at large scale in the network and continues in real-time without a fixed-term 
        * Process - 
          * Voting for Bookkepers by NEO token holders voting for those they support
          * Selected Bookkeepers reach consensus and generate New Blocks using a BFT algorithm
        * Security and Availability
          * Fault Tolerance - `f = (n - 1) / 3` for Consensus System with `n` Consensus Nodes
            * Resistant - resistant to general Byzantine failures and suitable for any network environment
            * Finality - prevents transactions from being revoked or rolled back after confirmations are finalised in a block
        * Performance
          * TODO

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

* [ ] - [NeoContract White Paper](http://docs.neo.org/en-us/index.html)
