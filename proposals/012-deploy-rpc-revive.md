# RFC-012: Deploy revive-rpc to Asset Hubs for MetaMask Support

## Summary
Deploy revive-rpc to all Asset Hubs to enable MetaMask and Web3
wallet compatibility for PolkaVM smart contracts. This is necessary to support
Ethereum compatibility on Asset Hubs and enable Solidity contracts to interact
with the chain.

## Details
IBP will deploy and maintain revive-rpc instances for:

### Production
- **Polkadot Asset Hub**:
    - `eth-asset-hub-polkadot.dotters.network`
    - `eth-asset-hub-polkadot.ibp.network`
- **Kusama Asset Hub**:
    - `eth-asset-hub-kusama.dotters.network`
    - `eth-asset-hub-kusama.ibp.network`

### Testnet
- **Paseo Passet Hub**:
    - `eth-passet-hub-paseo.dotters.network`
    - `eth-passet-hub-paseo.ibp.network`
- **Paseo Asset Hub**:
    - `eth-asset-hub-paseo.dotters.network`
    - `eth-asset-hub-paseo.ibp.network`

## Technical Requirements
- Deploy revive-rpc binary alongside existing RPC infrastructure
- Connect to local archive nodes
- Enable WebSocket support
- Standard monitoring and alerting

## Timeline
- **Immediate**: Deploy for Paseo Passet Hub and Kusama 
- **Upon pallet-revive deployment**: Deploy for Polkadot and Paseo Asset Hubs

## Benefits
- MetaMask compatibility for PolkaVM smart contracts
- Lower barrier for Ethereum developers
- Geographic distribution through IBP network

## Voting
Emoji **Yes** to approve or **No** to reject.
Voting closes **16 July 2025 23:59 UTC**.

## References
- [Polkadot Forum](https://forum.polkadot.network/t/testnets-paseo-officially-becomes-the-polkadot-testnet-temporary-passet-hub-chain-for-smart-contracts-testing/13209/3)
- [revive-rpc](https://github.com/hitchhooker/revive-rpc)
