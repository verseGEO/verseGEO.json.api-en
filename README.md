# verseGEO P2E API Guide

- Homepage : [verseGEO.com](http://versegeo.com/).
- Whitepaper : [verseGEO Whitepaper](http://versegeo.com/whitepaper-k.html).

## Introduction
verseGEO provides tokens and NFT models that can be used empirically based on verified game platforms and services. In addition, we provide a digital ecosystem that can integrate the real world and metaverse that integrates the fictional world and big data of each game that will be opened in stages.
  -	verseGEO supports various games and blockchain businesses.
  -	It can be used in various channels through tokenization for points or rewards of the game or contents service
  -	It supports the internal NFT marketplace that can issue, distribute and sell NFTs and external NFT marketplace.

   <img src="https://github.com/verseGEO/verseGEO.json.api-kr/blob/main/eco.png">


## WEB 3.0 Infra
This document solves the intrinsic issues and problems of blockchain such as slow networks and functional limitations of DAPP development, etc., and enables existing services and systems (games, shopping, SNS, etc.) It is intended to support. 

   <img src="https://github.com/verseGEO/verseGEO.json.api-kr/blob/main/web30.svg">

The Metaverse WEB3.0 Blockchain Platform(MW30P) facilitates WEB3.0-based provision and acceptance of various blockchain platforms through the acceptance and application of continuously developing blockchain and existing technologies and services.다.


## P2E Interface
A total of 6 APIs are provided. API is classified into Sync type and Async type in consideration of performance. Affiliates build functions corresponding to each API and process them.


| API | From | To | Function | Note |
|-----|--------|--------|------|------|
|Exchange Rate inquiry|Partners|MW30P|Item/Point/etc To PlayToken Exchange Rate Inquiry<br>PlayToken To Item/Point/etc Exchange Rate Inquiry<br>(Partner's various benefits to users, etc.)||
|Exchange|Partners|MW30P|Item/Point/etc To PlayToken Exchange<br>PlayToken To Item/Point/etc Exchange|Async|
|Passport|Partners|MW30P|Certification services for execution of key APIs||
|Withdrawal address|Partners|MW30P|거Verification and registration of externally available addresses held by users of the affiliate (withdrawal address)||
|Withdrawal pre-trade|Partners|MW30P|Withdrawal preliminary transactions||
|Withdrawal |Partners|MW30P|Withdraw withdrawable tokens(PlayToken) to an external address|Async|
|Block Notify|MW30P|Partners|Exchange API, Blockchain processing result of Withdrawal API sent (Confirm completed or not)|Async|
