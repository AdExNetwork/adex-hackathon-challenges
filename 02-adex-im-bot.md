# AdEx bot for Telegram/Status

An important part of the user flow of the [AdEx dapp](https://github.com/AdExNetwork/adex-dapp) is to submit transactions to confirm that your bids were executed (their goal was completed). The way this works is: the dapp connects to your own `adex-node`, and the node reports to you when the bid goals were actually executed. Then, you just relay that message to the chain by signing a `verifyBid()` transaction.

However, going into the app just to check if any bids need confirmation might be cumbersome.

Enter the AdEx bot: a Telegram/Status IM bot that connects with the `adex-node` and sends you messages when any bid is ready for confirmation.
