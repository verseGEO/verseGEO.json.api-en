# verseGEO P2E API Guide

- Homepage : [verseGEO.com](http://versegeo.com/).
- Whitepaper : [verseGEO Whitepaper](http://versegeo.com/whitepaper-k.html).

## 1. Exchange Rate API (Affiliates → MW30P)

The Exchange Rate Inquiry API must be called before converting Play Token for Item, Point, etc. of a game or service and refer to the exchange rate. The exchange rate referenced through the Exchange Rate inquiry is applied to the subsequent API, “Exchange Request API,” and can be converted into Play Token.

* REST API Interface Specification

| API | API URI |Method|Content-Type|
|-----|---------|------|------------|
|Exchange Rate API|/api/ExRate.json|POST|application/json|

  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/01REQ-01.Exchange_Rate.jpg" width="80%">
  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/01RES-01.Exchange_Rate.jpg" width="80%">
  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/01SEQ-01.Exchange_Rate.jpg">


## 2. Exchange API (Affiliates → MW30P)

After inquiring Exchange Rate, request to convert Item or Point into Play Token based on the received exchange rate. At this time, if the address for Play Token is not issued, the MW30P side automatically allocates the Play Token address. The item or point to be converted must calculate the corresponding quantity according to the exchange rate received from the Exchange Rate inquiry, and inform that the transaction is impossible if the quantity is less than the minimum quantity.

* REST API Interface Specification

| API | API URI |Method|Content-Type|
|-----|---------|------|------------|
|Exchange Request API|/api/ExReq.json|POST|application/json|

  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/02REQ-01.Exchange.jpg" width="80%">
  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/02RES-01.Exchange.jpg" width="80%">
  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/01SEQ-01.Exchange.jpg">


## 3. P2E Password Registration API (Affiliates → MW30P)

User password registration is required for P2E withdrawal. The affiliate receives the password from the user, verifies it, and stores it. In addition, the registration password is verified once by affiliates and twice by MW30P by making a registration request to MW30P. Passwords registered in MW30P apply secondary encryption (one-way) passwords encrypted by affiliates.

* REST API Interface Specification

| API | API URI |Method|Content-Type|
|-----|---------|------|------------|
|Password Registration API|/api/RegOutPasword.json|POST|application/json|

  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/03REQ-01.Password_registration.jpg" width="80%">
  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/03RES-01.Password_registration.jpg" width="80%">
  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/03SEQ-01.Password_registration.jpg">
  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/03SEQ-02.Password_change.jpg">


## 4. P2E Withdrawal Address Verification API (Affiliates → MW30P)

The P2E withdrawal address verification request is a function to verify the integrity of the Ethereum address required to transmit Play Tokens that can be used far within the Metaverse ecosystem, such as games or contents, to the blockchain public chain. P2E withdrawal address verification only checks the legitimacy of the address. Accordingly, the user must enter the P2E withdrawal address correctly. 

* REST API Interface Specification

| API | API URI |Method|Content-Type|
|-----|---------|------|------------|
|Withdrawal Address Verification API|/api/OutAddrVerify.json|POST|application/json|

  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/04REQ-01.Withdrawal_address_verification.jpg" width="80%">
  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/04RES-01.Withdrawal_address_verification.jpg" width="80%">
  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/04SEQ-01.Withdrawal_address_verification.jpg">
  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/04SEQ-02.Withdrawal_address_change.jpg">


## 5. P2E Withdrawal API (Affiliates → MW30P)

P2E withdrawal is a function that sends Play Token to an external Ethereum address. The P2E Token sent to the external Ethereum address can be freely used in various fields such as exchanges.

* REST API Interface Specification

| API | API URI |Method|Content-Type|
|-----|---------|------|------------|
|Withdrawal API|/api/ReqWithdraw.json|POST|application/json|

  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/05REQ-01.Withdrawal.jpg" width="80%">
  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/05RES-01.Withdrawal.jpg" width="80%">
  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/05SEQ-01.Withdrawal.jpg">
  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/05SEQ-02.Withdrawal.jpg">


## 6. Notification of Processing Result API (MW30P → Affiliates)

The processing result notification API provides the blockchain processing results of the Exchange request API and the P2E withdrawal request API to the affiliate server to prevent performance degradation due to the node delay of the blockchain. The affiliate server updates the status of the corresponding txid of the exchange request and the P2E withdrawal request with the received processing result notification.

* REST API Interface Specification

| API | API URI |Method|Content-Type|
|-----|---------|------|------------|
|Notification of Processing Result API|/api/Channel Request URL.json|POST|application/json|
  
  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/06REQ-01.Back-end_Notify.jpg" width="80%">
  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/06RES-01.Back-end_Notify.jpg" width="80%">
  <img src="https://github.com/verseGEO/verseGEO.json.api/blob/main/src/06SEQ-01.Back-end_Notify.jpg">
  
  
