# Report Protocols

 - [**ColoredConis**](http://coloredcoins.org) 
 - [**Rootstock**](https://www.rsk.co)
 - [**OpenAssets**](http://www.openassets.org)  :star::star:
 - [**Omnilayer**](http://www.omnilayer.org)    :star::star::star:
 - [**CounterParty**](https://counterparty.io)  :star::star::star::star:
 

## ColoredCoins

In January 2018 the ColoredCoins node stopped working. :scream:

## Rootstock RSK

>Rootstock (RSK) is a smart contract platform that is connected to the Bitcoin blockchain through sidechain technology. Although **the smart contracts aren't actually deployed on the Bitcoin blockchain itself**, RSK allows users to send Bitcoin directly onto the Rootstock chain through a 2-way peg,

## Omni Layer (*Mastercoin*)

>Bitcoin has some little-known advanced features (such as scripting) which many people imagine will enable it to perform fancy new tricks someday. The Omni Protocol uses exactly NONE of those advanced features, because support for them is not guaranteed in the future, and the Omni Protocol doesn't need them to embed data in the block chain. 

 - Initial Token Distribution via the “Exodus Address”

 - Transaction Type:
     + Class A: *deprecated*
     + Class B: multisig
         * Class B transactions attempt to address the UTXO ‘bloat’ issue by storing data in the blockchain by utilizing ‘1-of-n’ multisignature outputs where one of the signatories is the sender or another public key address the sender has designated.
     + Class C: `OP_RETURN`

 - Implementations:
     + [OmniCore](https://github.com/OmniLayer/omnicore) [C++] Fork of Bitcoin Core
         * Disclaimer: This software is EXPERIMENTAL software. USE ON MAINNET AT YOUR OWN RISK.
     + [OmniClientJS](https://github.com/OmniLayer/OmniClientJS) [Node.js]
     + [OmniCore Lite](https://github.com/OmniLayer/omnicore-lite) [C++]
         * Litecoin implementation *work in progress*
 
 - Explorers
     + [OmniExplorer](https://github.com/OmniLayer/omniexplorer) 

 - Wallets:
     + [OmniWallet](https://github.com/OmniLayer/omniexplorer) [Python + AngularJS]
     + [OmniJ](https://github.com/OmniLayer/OmniJ) [Java] *Experimental*

#### Pro/Cons
- Pro:
    + Used by Theter
    + Most used
- Cons:
    + **Need a fork of bitcoin core for working**
    + Slow explorer
    

## Open Assets

>The Open Assets Protocol is a simple and powerful protocol built on top of the Bitcoin Blockchain. It allows issuance and transfer of user-created assets. The Open Assets Protocol is an evolution of the concept of colored coins.

 - Transaction type: `OP_RETURN`

 - Implementations: 
     + [Open Assets Reference Implementation](https://github.com/OpenAssets/openassets) [Python]
        * Last commit: Nov 2, 2014
        * The `protocol submodule` implements the specification in order to interpret Bitcoin transactions as Open Assets transactions.
        * The `transactions submodule` contains functions that can be used to build unsigned Open Assets transactions for various purposes.

     + [openassets-js](https://github.com/OpenAssets/openassets-js) [JavaScript] *work in progress*
     Last commit: May 11, 2015

 - Wallets: 
     + [Colorcore](https://github.com/OpenAssets/colorcore) [Python]
         * A client providing a command line and RPC interface for performing operations through the Open Assets Protocol
         * Last commit: Nov 26, 2014
         * Command-line interface
         * JSON/RPC interface is suitable for server-side implementations
     + [Coinprism](https://www.coinprism.com) web-wallet + full block explorer (closed source)
         * Features
             - Issue any assets
             - Send and receive assets and bitcoins
             - Full block explorer
             - Two-factor authentication
             - Export and backup wallet
             - Import private key
             - Issue bitcoin and colored coin dividends
             - Optional miners' fee
             - Offline storage (Armory, TREZOR)
             - [Android App](https://github.com/Coinprism/android-wallet)

#### Pro/Cons
 - Pro:
     + Direct connection to bitcoin core node
     + Python 3
 - Cons:
     + Small community if any :sweat_smile:
     + Not updated wallet
    
## Counterparty

>Counterparty is an **open-source**, **non-profit** project which relies heavily on its community. This makes the official public forum the best place to provide support for any issues encountered while using Counterparty software or protocol.

>Counterparty embeds data into regular Bitcoin transactions. To a regular Bitcoin client, these transactions look like normal Bitcoin transactions, with one party sending another party a very small amount of Bitcoin. A Counterparty node (which runs the Bitcoin client along with the Counterparty client software) will recognize and interpret the data in these Bitcoin transactions based on specific rules. From this, it constructs its own ledger of Counterparty transactions that it has seen on the Bitcoin network.

Counterparty has generous [bug bounty program](https://counterparty.io/docs/bounties/).

#### Architecture
![alt](https://raw.githubusercontent.com/CounterpartyXCP/Documentation/master/_images/platform_architecture.png)

#### Token creation
>Alphanumeric assets require a anti-spam fee of 0.5 XCP.
Subassets require a anti-spam fee of 0.25 XCP.
Numeric assets are free and require only a Bitcoin miners fee.

#### Lightning network
>Work on the upcoming Lightning Network promises to enable nearly instant, cheap and safe exchange of bitcoin between untrusted counterparties.

>Features in Counterparty are under development that will allow for use of uni- or bi-directional payment channels with Counterparty tokens.

#### Multisignature Addresses
>Multisignature transactions require signatures from more than one Bitcoin private key to spend their funds. Counterparty supports various multisignature schemes, such as 1-of-3, 2-of-3, 3-of-5, and more.

#### CIPs
Counterparty has a [Counterparty Improvement Proposals](https://github.com/CounterpartyXCP/cips) process

 - Transaction Type:
     + `OP_RETURN`
     + `multisig`
     + `pubkeyhash`

 - Wallets: 
     + [CounterWallet](https://github.com/CounterpartyXCP/counterwallet) [JavaScript]
         * Fully functional wallet for BTC, XCP, and user-created tokens
         * Peer-to-peer asset trading with algorithmic order matching (XCP, other assets)
         * Custom asset creation
         * Betting
         * Broadcasting data on the Bitcoin Blockchain
         * Multisig
         * Offline (Armory) transactions
     + [...](https://counterparty.io/wallets)
 - Explorers:
     + [Blockparty](https://github.com/CounterpartyXCP/blockparty) Last commit Aug 22, 2014
     + [xchain](https://xchain.io/)

#### Pro/Cons
- Pro:
    + [Support](https://counterpartytalk.org)
    + Lightning Network support in development
    + More transaction type support
- Cons:
    + Token creation with alphanumeric name require an "una tantum" anti-spam fee of 0.5 XCP.
    + Require [btcdrak](https://github.com/btcdrak/bitcoin/releases) a bitcoin core fork