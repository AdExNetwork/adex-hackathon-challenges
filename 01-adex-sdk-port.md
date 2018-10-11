# AdEx SDK port to another platform

At the moment, the AdEx SDK is implemented for the browser only: https://github.com/AdExNetwork/adex-adview (please note, there's also an `adex-sdk` repo, which is no longer relevant, as it was replaced by `adex-adview`).

The AdEx SDK has the responsibility of showing an ad, and tracking impressions and clicks and sending them to the `adex-node`. It also generates a random Ethereum (secp256k1) keypair the first time it runs on your browser, and uses that keypair to sign impression/click events, allowing us to identify which anonymous user ID sent which event later on the server.

In order to implement this for another platform, you will need to:

1. Create a keypair for the user and persist it, if one isn't persisted already
2. connect to the `adex-node` and pull a list of bids
3. pick one at random to display, and show it's banner (adunit image URL, which resides in IPFS); use an IPFS gateway for convenience
4. when an impression happens, or a click, create a signed event and send it to the `adex-node`


## End goal

Re-implement the `adex-adview` for another platform, for example Android or iOS.

## Resources

[adex-adview](https://github.com/AdExNetwork/adex-adview)

[adex-node](https://github.com/AdExNetwork/adex-node)
