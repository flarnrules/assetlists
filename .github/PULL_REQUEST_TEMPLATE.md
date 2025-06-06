## Description

<!-- Please specify added token and its corresponding chain. (recommended one token at a time) -->
<!-- E.g., Adding chain: Bar  -->
<!-- E.g., Adding token: FOO from chain Bar  -->
<!-- E.g., See FOO/OSMO Pool 1000 -->

## Checklist

<!-- The following checklist can be ticked after Creating the PR -->

### Adding Assets

<!-- If NOT adding a new asset, please remove this 'Adding Chains' section. -->
If adding a new asset, please ensure the following:
- [ ] Asset is registered to the [Cosmos Chain Registry](https://github.com/cosmos/chain-registry).
- [ ] Add asset to bottom of `zone_assets.json`.
   - [ ] `chain_name` and `base_denom` are provided and use values exactly as defined at the Chain Registry.
   - [ ] `path` is provided, and the IBC channel referenced is registered at the Chain Registry (skip if native to Osmosis).
   - [ ] `osmosis_verified` is set to `false`
   - [ ] Optional: `transfer_methods`, `peg_mechanism`, `override_properties`, `canonical`, `categories`, where necessary (see [README](https://github.com/osmosis-labs/assetlists/tree/main?tab=readme-ov-file#how-to-add-assets) for details).
- [ ] I am aware that upgrading an asset to 'Verified' status requires an additional PR to this repo (checklist below).  

### Adding Chains

<!-- If NOT adding a new chain, please remove this 'Adding Chains' section. -->
If adding a new chain, please ensure the following:
- [ ] Chain is registered to the [Cosmos Chain Registry](https://github.com/cosmos/chain-registry).
   - Chain's registration must have `staking` defined, with at least one `staking_token` denom specified.
   - Chain's registration must have `fees` defined; at least one fee token has low, average, and high gas prices defined.
- [ ] IBC Connection between chain and Osmosis is registered.
- [ ] Add chain to bottom of `zone_chains.json`
   - [ ] `rpc` and `rest` does not have any CORS blocking of the Osmosis domain, and RPC node has have WSS enabled.
   - [ ] `explorer_tx_url` correctly directs to the transaction when the hash is inserted into the URL.

### Upgrading Asset to Verified

<!-- If NOT upgrading asset status, please remove this 'Upgrading Asset to Verified' section. -->

If upgrading an Asset to Verified, please see the requirements specified at [LISTING](https://github.com/osmosis-labs/assetlists/blob/main/LISTING.md#upgrade-asset-to-verified-status-permissioned), and ensure the following:
- [ ] Asset is defined thoroughly at the [Cosmos Chain Registry](https://github.com/cosmos/chain-registry).
   - [ ] A meaningful `description` (and `extended_description`, unless: meme or variant/derivative asset).
   - [ ] Associated `socials`, including `website` and `twitter` (unless: meme or variant/derivative asset).
   - [ ] **Logo Image** has a square Aspect Ratio, < 250 KB file size, and appropriate visual contrast with Osmosis Zone's colors.
- [ ]  **Liquidity**: This pool meets the liquidity requirements, and has a +-2% depth of $50 (~$5k full range liq.) (Provide Pool ID): ______ (Skip if alloy constituent)

'Verified' Status Validation Checklist (to be completed by Osmosis Zone maintainers):
- [ ] Verify appearance and metadata
- [ ] Accurate Price
- [ ] Trading and routing functionality
   - [ ] $50 USDC offer yields at least $49-worth of this Asset
- [ ] Withdraw and Deposit
   - [ ] Deposit Transaction URL (if in-app)

