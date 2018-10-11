# Simple AdEx Protocol dapp

The existing [adex-dapp](https://github.com/AdExNetwork/adex-dapp) is implemented on our own [adex-core](https://github.com/AdExNetwork/adex-core). However, there is a new version of the protocol, right here: [adex-protocol-eth](https://github.com/AdExNetwork/adex-protocol-eth).

The goal of this challenge is to implement a very simple dApp over the AdEx Protocol smart contracts.

It needs to allow:

1. Advertiser side: Upload ad banners to IPFS
2. Advertiser side: Create a bid and sign it using `adex-protocol-eth/js/bid.js`
3. Publisher side: pick a bid and create an on-chain commitment for it by calling `commitmentStart` on the smart contract; for simplicity, assign the publisher and the advertiser as the two validators.
4. Both sides: sign a commitment vote and submit it via `commitmentFinalize` once both signatures are collected
5. Both sides: deposit and withdraw tokens


Note: bids and their signatures need to be saved off-chain. For this, you can create your own simple back-end, use a back-end as a service, or, if you're feeling adventurous, broadcast them in a p2p way using Swarm or IPFS pubsub.
