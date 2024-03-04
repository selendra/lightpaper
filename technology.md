**Technology**

**Substrate-based architecture**

Selendra is a proof-of-stake network built on Substrate, utilizing GRANDPA for finality and BABE for block production as consensus mechanisms. It incorporates various general pallets, core libraries, and a forkless runtime, along with Frontier for EVM compatibility. Below is the summary of Selendra's architecture based on the Substrate:

**Core Client Libraries**:



* Responsible for outer node services like peer discovery, managing transactions, achieving consensus, and handling RPC calls.
* Utilizes Rust crates with the sc_ prefix for functionalities such as building the networking layer and managing communication between network participants.

**FRAME Libraries for the Runtime**:



* Enable the construction of runtime logic, encoding/decoding information, and declaring runtime storage items.
* Identified by the frame_ prefix in the crate name, these libraries provide the infrastructure for the runtime and include pallet_* libraries representing FRAME modules.

**Primitive Libraries**:



* Control underlying operations at the lowest level and facilitate communication between core components within the architecture.

**Substrate Node**:



* Comprises two main parts: a core client with outer node services and the runtime.
* The runtime defines rules for state transitions on-chain and compiles to WebAssembly (Wasm) bytecode, allowing forkless upgrades and multi-platform compatibility.

**Customization Levels**:



* **Substrate Node**: Provides prebuilt functionality with default implementations for basic components.
* **FRAME**: Allows building a Substrate runtime from prebuilt templates by adding pallets to customize blockchain logic.
* **Substrate Core**: Offers high technical freedom but requires more work to implement custom runtimes targeting WebAssembly while adhering to Substrate's block creation principles.

Selendra's architecture leverages Substrate's flexibility to enable developers to create customized blockchains by utilizing different levels of abstraction, libraries tailored for specific functionalities, and compatibility with WebAssembly for efficient blockchain development. The main objective of Selendra is to be a compatible EVM and Wasm smart contract network, allowing developers to build efficient blockchain applications with ease.



**Wasm and EVM support and other features **

Selendra Network embraces both WebAssembly (Wasm) and Ethereum Virtual Machine (EVM) environments, enabling developers to leverage familiar tools and programming languages across multiple platforms and chains. This support allows for seamless development and deployment of smart contracts on diverse blockchain ecosystems

**Key Features**

**1. Multi-Virtual Machine and Multi-Chain Support:**

Selendra Network facilitates development on various platforms by supporting both EVM and Wasm environments. This feature empowers developers to utilize their existing knowledge and tools to build applications across different chains, enhancing flexibility and accessibility.

**2. Scalability:**

Unlike traditional blockchains that require hard forks for upgrades, Selendra Network ensures scalability without compromising security. Through a forkless runtime upgrade mechanism, the network can scale efficiently, leading to faster transactions and an improved user experience.

**3. Interoperability:**

To amplify collaboration among different blockchains and smart contracts, Selendra will blend Cross-Virtual Machine (XVM) from Astar Network, a network also built on Substrate. This feature permits smooth communication and interaction across diverse blockchain networks, fostering an ecosystem with enhanced connectivity.

**4. Selendra zkEVM:**

Selendra Network will introduce Selendra zkEVM, a zero-knowledge Ethereum Virtual Machine (EVM) that offers scalability and privacy advantages for developers and users. This innovative solution enhances data privacy while maintaining the benefits of the EVM environment, catering to the evolving needs of the blockchain community[1].

Selendra's commitment to supporting multiple virtual machines, ensuring scalability through forkless upgrades, promoting interoperability with XVM, and introducing privacy-focused solutions like Selendra zkEVM showcases its dedication to advancing blockchain technology with a focus on efficiency, security, and innovation.


### List of tools from Substrate used for Selendra so far

[+] Substrate general pallett:
  - frame_system
  - pallet_timestamp,
  - pallet_scheduler,
  - pallet_preimage,
  - pallet_balances
  -  pallet_transaction_payment: 

[+] Substrate Staking and consensus
  - pallet_authorship
  - pallet_babe
  - pallet_staking
  - pallet_offences
  - session_historical
  - pallet_session
  - pallet_grandpa
  - pallet_im_online
  - pallet_authority_discovery
  - pallet_election_provider_multi_phase
  - pallet_bags_list
  - pallet_fast_unstake
    
[+] Substrate Governance
  - pallet_treasury: It like pot that keep balance from slash and other (our chain most of balance are burn not go here)
  - pallet_conviction_voting
  - pallet_referenda
  - pallet_whitelist
  - pallet_sudo
  - pallet_bounties: Request token from treasury
  - pallet_child_bounties

[+] Substrate utility
  - pallet_utility
  - pallet_multisig
  - pallet_recovery
  - pallet_proxy
  - pallet_indices
  - pallet_identity
  - pallet_vesting

[+] Substrate Evm
  - pallet_evm: the EVM pallet uses [SputnikVM](https://github.com/rust-blockchain/evm) as the underlying EVM engine The engine is overhauled so that it's [modular](https://github.com/corepaper/evm)
  - pallet_ethereum: The Ethereum pallet works together with EVM pallet to provide full emulation for Ethereum block processing
  - pallet_base_fee: handle fee on pallet evm
  - pallet_custom_signatures: transter between evm and substrate account

[+] Asset and contract
  - pallet_contracts
  - pallet_assets: create asset without have to write code.
      - plan: can trasaction via evm and pallet-contract (use pallet-xvm adopting astart)


