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


| API | 요청 | 처리 | 기능 | 비고 |
|-----|--------|--------|------|------|
|Exchange Rate inquiry|Affiliates|MW30P|Exchange exchange rate inquiry to convert Game Item and Point into Play Token (internal token)||
|Exchange|Affiliates|MW30P|Convert Game Item or Point to Play Token (internal token) according to the specified exchange rate|Async|
|Request for verification of withdrawal address|Affiliates|MW30P|거Verification of Ethereum addresses held by individual users that can be used for exchanges, etc.||
|Password registration|Affiliates|MW30P|Password registration to verify the legitimacy of the withdrawal request||
|Withdrawal |Affiliates|MW30P|PRequest withdrawal of Play Token (internal token) to the registered withdrawal address|Async|
|Transmitting the processing result(Back-end Notify)|MW30P|Affiliates|Transmitting the processing history of the execution result for the full text of Exchange request and withdrawal request|Async|


## 1. Exchange Rate API (Affiliates → MW30P)

The Exchange Rate Inquiry API must be called before converting Play Token for Item, Point, etc. of a game or service and refer to the exchange rate. The exchange rate referenced through the Exchange Rate inquiry is applied to the subsequent API, “Exchange Request API,” and can be converted into Play Token.

* REST API Interface Specification

| API | API URI |Method|Content-Type|
|-----|---------|------|------------|
|Exchange Rate API|/api/ExRate.json|POST|application/json|


## 2. Exchange API (Affiliates → MW30P)

After inquiring Exchange Rate, request to convert Item or Point into Play Token based on the received exchange rate. At this time, if the address for Play Token is not issued, the MW30P side automatically allocates the Play Token address. The item or point to be converted must calculate the corresponding quantity according to the exchange rate received from the Exchange Rate inquiry, and inform that the transaction is impossible if the quantity is less than the minimum quantity.

* REST API Interface Specification

| API | API URI |Method|Content-Type|
|-----|---------|------|------------|
|Exchange Request API|/api/ExReq.json|POST|application/json|


## 3. P2E Password Registration API (Affiliates → MW30P)

User password registration is required for P2E withdrawal. The affiliate receives the password from the user, verifies it, and stores it. In addition, the registration password is verified once by affiliates and twice by MW30P by making a registration request to MW30P. Passwords registered in MW30P apply secondary encryption (one-way) passwords encrypted by affiliates.

* REST API Interface Specification

| API | API URI |Method|Content-Type|
|-----|---------|------|------------|
|Password Registration API|/api/RegOutPasword.json|POST|application/json|


## 4. P2E Withdrawal Address Verification API (Affiliates → MW30P)

The P2E withdrawal address verification request is a function to verify the integrity of the Ethereum address required to transmit Play Tokens that can be used far within the Metaverse ecosystem, such as games or contents, to the blockchain public chain. P2E withdrawal address verification only checks the legitimacy of the address. Accordingly, the user must enter the P2E withdrawal address correctly. 

* REST API Interface Specification

| API | API URI |Method|Content-Type|
|-----|---------|------|------------|
|Withdrawal Address Verification API|/api/OutAddrVerify.json|POST|application/json|


## 5. P2E Withdrawal API (Affiliates → MW30P)

P2E withdrawal is a function that sends Play Token to an external Ethereum address. The P2E Token sent to the external Ethereum address can be freely used in various fields such as exchanges.

* REST API Interface Specification

| API | API URI |Method|Content-Type|
|-----|---------|------|------------|
|Withdrawal API|/api/ReqWithdraw.json|POST|application/json|


## 6. Notification of Processing Result API (MW30P → Affiliates)

The processing result notification API provides the blockchain processing results of the Exchange request API and the P2E withdrawal request API to the affiliate server to prevent performance degradation due to the node delay of the blockchain. The affiliate server updates the status of the corresponding txid of the exchange request and the P2E withdrawal request with the received processing result notification.

* REST API Interface Specification

| API | API URI |Method|Content-Type|
|-----|---------|------|------------|
|Notification of Processing Result API|/api/Channel Request URL.json|POST|application/json|
