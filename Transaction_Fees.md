- Help secure the network. If fees were nothing, people spam payments back to themselves and flood the network with DoS attack.
- Transaction fees go into a rewards pot. Any fees collected during the epoch increase the rewards give to people staking on Cardano.
- Staking rewards that come from the reserve will go down over time. As transaction volume increases over time on Cardano, fees can make up this difference for people staking.
- Based on protocol parameters so they can be voted on and changed in the future.

How are Fees calculated?
`mininumFee = txFeeFixed + (txFeePerByte * TX_BYTES)`
`txFeeFixed`: value in lovelace

```json
{
  "txFeePerByte": 44,
  "minUTxOValue": 1000000,
  "stakePoolDeposit": 500000000,
  "decentralization": 0,
  "poolRetireMaxEpoch": 18,
  "extraPraosEntropy": null,
  "stakePoolTargetNum": 500,
  "maxBlockBodySize": 65536,
  "maxTxSize": 16384,
  "treasuryCut": 0.2,
  "minPoolCost": 340000000,
  "maxBlockHeaderSize": 1100,
  "protocolVersion": {
    "minor": 0,
    "major": 4
  },
  "txFeeFixed": 155381,
  "stakeAddressDeposit": 2000000,
  "monetaryExpansion": 3.0e-3,
  "poolPledgeInfluence": 0.3
}
```

```json
{
  "type": "Tx MaryEra",
  "description: "",
  "cborHex": "78dhdh83hdhauhbfdh832yfh9whfhwe8ff..."
}
```

`cborHex` is `TX_BYTES`. The actual bytes that will be stored on the blockchain. For example: it is 756 bytes
`mininumFee = 155381 + (44 * 756) = 188645 lovelace = 0.188645 ADA`.
