# LUD-09: successAction `url` Tag Support

Does the wallet display the `successAction` URL (description + clickable link) to the user after a successful LNURL-pay payment?

Spec: [LUD-09](https://github.com/lnurl/luds/blob/luds/09.md)

The `successAction` field with tag `url` allows a payment recipient to return a description and URL to the sender after payment. This is useful for receipts, order confirmations, digital content delivery, and more. Wallets that support this display the description and offer to open the URL. Wallets that don't simply show a generic "payment sent" screen.

## Tested

| Wallet | Should Support | Tested | Notes |
|--------|:--------------:|:------:|-------|
| [Alby Go](https://getalby.com/products/alby-go) | YES | Pass | Description + "Open Link" button |
| [Blink](https://www.blink.sv/) | YES | Pass | |
| [Blitz](https://blitz-wallet.com/) | YES | Pass | Opens URL in in-app WebView, tested by Blitz team |
| [Breez](https://breez.technology/) | YES | Pass | Tested with Misty Breez |
| [Phoenix](https://phoenix.acinq.co/) | YES | Pass | |
| [Wallet of Satoshi](https://www.walletofsatoshi.com/) | Unknown | Pass | Closed source |
| [Zeus](https://zeusln.app/) | YES | Pass | Description + clickable URL via `Linking` |
| [Blockstream Green](https://blockstream.com/green/) | YES | N/A | Has SDK model but UI doesn't support sending to Lightning addresses |
| [Cake Wallet](https://cakewallet.com/) | NO | N/A | No UI rendering of successAction; amount bug prevents send |
| [Primal](https://primal.net/) | YES | N/A | Uses Breez SDK, but payment errored during test |
| [River](https://river.com/) | Unknown | N/A | Unable to pay a Lightning address |
| [Bitkit](https://bitkit.to/) | NO | Fail | No LNURL code found in repo |
| [Bitnob](https://bitnob.com/) | Unknown | Fail | Closed source |
| [Blue Wallet](https://bluewallet.io/) | YES | Fail | Code exists but doesn't display in practice (via LNDHub) |
| [Coinos](https://coinos.io/) | Unknown | Fail | Web-based |
| [Fedi](https://www.fedi.xyz/) | NO | Fail | Doesn't parse successAction from response at all |
| [Flash](https://getflash.io/) | YES | Fail | Has Breez SDK but doesn't surface URL in UI |
| [Minibits](https://www.minibits.cash) | NO | Fail | Has LNURL-pay but never processes successAction |
| [Strike](https://strike.me/) | Unknown | Fail | Closed source |

## Untested

| Wallet | Should Support | Notes |
|--------|:--------------:|-------|
| [Blixt](https://blixtwallet.github.io/) | YES | Description + URL link + Copy/Open buttons in code |
| [Aqua](https://www.aquawallet.io/) | NO | Has data model but no UI rendering of successAction |
| [Electrum](https://electrum.org/) | NO | No successAction handling in code |
| [Lexe](https://lexe.app) | NO | Has LNURL-pay but no successAction rendering |
| [Muun](https://muun.com/) | NO | No LNURL-pay code found |
| [ShockWallet](https://shock.network) | NO | Passes data through but no UI rendering |
| [Amber](https://amber.app/amberwallet) | Unknown | Closed source |
| [Bipa](https://bipa.app/) | Unknown | Closed source |
| [CashApp](https://cash.app/) | Unknown | Closed source |
| [Machankura](https://8333.mobi/) | Unknown | USSD can't display URLs, but also has WhatsApp UI and mobile apps that could |
| [Satoshi](https://satoshi.money/) | Unknown | Closed source |
| [Speed](https://www.speed.app/) | Unknown | Closed source |
| [Volt](https://volt.finance) | Unknown | No code found |
| [ZBD](https://zbd.gg/) | Unknown | Closed source |

## Summary

- **Pass (7):** Alby Go, Blink, Blitz, Breez, Phoenix, Wallet of Satoshi, Zeus
- **Fail (8):** Bitkit, Bitnob, Blue Wallet, Coinos, Fedi, Flash, Minibits, Strike
- **N/A (4):** Blockstream Green, Cake Wallet, Primal, River
- **Should support, untested (1):** Blixt
- **Should NOT support (6):** Aqua, Cake Wallet, Electrum, Lexe, Muun, ShockWallet
- **Unknown (8):** Remaining closed-source or no-code-found wallets (includes Machankura)

## Methodology

"Should Support" is determined by reviewing the wallet's open-source code for successAction handling. "Tested" is a real-world test: send a payment to an LNURL-pay endpoint that returns a `successAction` with tag `url`, and check whether the wallet displays the description and link.

## Last updated

2026-04-03
