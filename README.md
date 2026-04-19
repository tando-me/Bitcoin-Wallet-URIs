# Bitcoin Wallet Compatibility

A crowdsourced compatibility tracker for Bitcoin and Lightning wallet features. Think [caniuse.com](https://caniuse.com) but for LNURL, BOLT, and BIP specs across wallets, nodes, and services.

Each feature is tracked at three levels:
1. **What the spec defines** -- the protocol standard
2. **What the source code implements** -- "Should Support" based on code review
3. **What actually works when tested** -- real-world Pass/Fail verification

## Feature Tracking

### URI Schemes
- [URI Schemes](uri-schemes.md) -- `lightning:`, `bitcoin:`, and wallet-specific URI handlers registered in mobile OS
- [URI Test Suite](uri-test.html) -- tap-through test page to verify each wallet's registered scheme on a mobile device

### LNURL (LUD)
- [LUD-09: successAction `url` tag](lnurl/lud-09-successAction.md) -- does the wallet display a URL + description after payment?

## Contributing

PRs welcome. To add test results:
1. Test the feature with the wallet
2. Update the relevant table with Pass/Fail/N/A
3. Add notes on what you observed

To add a new wallet or feature, follow the existing table format.
