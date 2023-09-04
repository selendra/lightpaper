## What are the Substrate Frame Pallets used to build Selendra? Can you help list all the Frame Pallets used to create Selendra? 


### Are these pallets used? If the pallets listed below are not used please noted not use.

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

