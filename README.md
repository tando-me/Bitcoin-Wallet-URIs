# Bitcoin-Wallet-URIs
A collection of known URIs that Bitcoin Wallet apps register within mobile OS's as Launch Services

Early Bitcoin adopters tend to install and test many different bitcoin apps on their smartphones. On iOS this can become a problem as there is no *easy* way to choose a default app to handle requests from other apps for payments. For example App X presents the user with a button to "Pay Lightning Invoice" and when you click on it, it opens a default wallet that is associated within the OS to handle the ```lightning:``` URL. There's currently no way to change the default on iOS

MoneyBadger (fka CryptoConvert) figured out a solution for iOS to give users the ability to choose an installed app to handle clicking a specific URI (```lightning:```). See their working app: https://apps.apple.com/in/app/cryptoqr-pay/id1617778619

Apparently each app can register not just as a handler for ```lightning:``` but can also register domain specific URI for their wallet, so an app could register to handle a ```walletofsatoshi:``` URI as an example.

If you as an app developer know to look for these domain-specific URI's, you could give your users the ability to choose a default app when handling ```lightning:``` URIs. The only problem is that there is no known repository of all the domain-specific URI's that are in use by all of the different wallet apps, and so everyone is left guessing. The repo is an attempt to collect all known URIs for all wallets to that you can give your (iOS) users choices on which app they want to associate with lightning payments.

See also:

https://developer.apple.com/documentation/coreservices/launch_services

https://docs.lightning.engineering/the-lightning-network/payment-lifecycle/understanding-lightning-invoices#uri-scheme
