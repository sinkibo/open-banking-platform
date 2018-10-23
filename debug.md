---

copyright:
  years: 2018
lastupdated: "2018-10-23"

---

<!-- Common attributes used in the template are defined as follows: -->
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}

# Debug messages

The Open Banking Platform service may return messages that will provide debug information about a current process.

## IOBP-D-001

CouchDbManager.getBankURL for messageType {} `<messageType>`

### Description

Fetching the bank URL from the database given the message type: `<messageType>`.

## IOBP-D-002

Sending to {}, `<urlValue>`

### Description

Indicates that the request is being sent to bank `<urlValue>`.

## IOBP-D-003

CouchDbManager.putBankResponse for transactionId, `<transactionId>`

### Description

Updates the transactions database with the bank response metadata.

## IOBP-D-004

CouchDbManager.putBankResponse Transaction Found: `<json>.toString()`

### Description

Indicates the transaction with the given transationId is found.

## IOBP-D-005

CouchDbManager.putBankResponse Transaction Found: `<json>.toString()`

### Description

Indicates the transaction with the given transationId is found.

## IOBP-D-006

CouchDbManager.getCouchDbProperties for database: `<db>`

### Description

Fetching the couchdb properties to connect to database: `<db>`.

## IOBP-D-007

=====>CouchDbManager.getCouchDbProperties properties for database [`<db>`], host [`<host>`], port [`<port>`], username [`<username>`]

### Description

Logging the CouchDb properties for database [`<db>`], host [`<host>`], port [`<port>`], username [`<username>`].

## IOBP-D-008

CouchDbManager.getBankInfo for x-fapi-financial-id: `<fapiFinId>`

### Description

Calling CouchDbManager.getBankInfo for given x-fapi-financial-id: `<fapiFinId>` to retrieve the bank information.

## IOBP-D-009

returnString {} , `<returnString>`

### Description 

Logging the return string.

## IOBP-D-010

Message sent and waiting for reply

### Description

Indicates that the Message is sent and waiting for reply from the bank.

## IOBP-D-011

Reponse `<responseEntity.getStatusCode()>` -  `<responseEntity.getBody()>`

### Description

Logging the metadata of the response for debugging purposes.

## IOBP-D-012

Now publish

### Description

Indicates that the component is now publishing messages to the queue.

## IOBP-D-013

[*] Waiting for messages. To exit, press CTRL+C

### Description

Indicates the returner is connected to rabbitmq and waiting to consume messages.

## IOBP-D-014

Payments.getBanks

### Description

Request processing to get the list of banks has started.

## IOBP-D-015

=====> Payments.getBanks.end

### Description

Request processing to get the list of banks has ended.

## IOBP-D-016

=====> Resolve Banks

### Description

Indicates the list of banks retrieved from the database.

## IOBP-D-017

[PaymentsService] (createPaymentSubmission) payment submission started, `<transactionId>`

### Description

Indicates [PaymentsService] (createPaymentSubmission) payment submission started, `<transactionId>.

## IOBP-D-018

[PaymentsService] (createPaymentSubmission) payment submission completed successfully `<transactionId>`

### Description

Indicates [PaymentsService] (createPaymentSubmission) payment submission completed successfully, `<transactionId>`.

## IOBP-D-019

json[code], messageType, transactionId

### Description

Indicates the json[code], messageType, transactionId for the current request being processed.

## IOBP-D-020

`<messageType>` + ended with ERROR, `<transactionId>`

### Description

Indicates the request processing for `<messageType>` + ended with ERROR, assigned with `<transactionId>`.

## IOBP-D-021

Payment init started, `<transactionId>`

### Description

Indicates the request processing got payment init started, assigned with `<transactionId>`

## IOBP-D-022

Sending response `<%s>`, JSON.stringify( response ), `<transactionId>`

### Description

Indicates the sending response `<%s>`, JSON.stringify( response ), `<transactionId>`.

## IOBP-D-023

Redirect\_url: `<url>`, `<transactionId>`

### Description

Indicates the redirect\_url: `<url>`, for the transaction `<transactionId>`.

## IOBP-D-024

`<messageType>` ended, `<transactionId>`

### Description

Indicates the request processing for `<messageType>` ended, assigned with `<transactionId>`.

## IOBP-D-025

Connected to the database `<db>`

### Description

Connected successfully to the backend database: `<db>`.

## IOBP-D-026

CouchDbManager.getBankInfo for x-fapi-financial-id: `<fapiId>`

### Description

Gets the bank information given the x-fapi-financial-id: `<fapiId>`.

## IOBP-D-027

Bank information for the given X-FAPI-FINANCIAL\_ID `<fapiId>` does not exist

### Description

The database does not contain information matching the given x-fapi-financial-id: `<fapiId>`.

## IOBP-D-028

Connected to the transactions database in Couchdb

### Description

Indicates that the connection to the couchdb db is successful.

## IOBP-D-029

CouchDbManager.putBankResponse Transaction found for the transactionId

### Description

Indicates the transaction record matching the transactionId `<transactionId>` is found in the transactions database.

## IOBP-D-030

Updated bank response to the transaction history database

### Description

Indicates the transaction record matching the transactionId `<transactionId>` is updated with the bank response metadata.

## IOBP-D-031

Parsing the http headers

### Description

Parsing the http headers to send it as part of the http request to the bank.

## IOBP-D-032

PSD2BankMessageHandler.sendMessage(), response received from the bank

Indicates that a n http response is received from the bank.

## IOBP-D-033

SecureSocketManager.getRestTemplate() is called

### Description

SecureSocketManager.getRestTemplate() is called to assemble the http request to be sent to the bank.

## IOBP-D-034

SecureSocketsManager.getSSLContext for bank: `<bankId>`

### Description

SecureSocketsManager.getSSLContext for the bank is created by loading the corresponding keystore given the bankId.

## IOBP-D-035

SecureSocketsManager.getSSLContext passphrase: `<passphrase>`,keystore: `<keystore>`

### Description

Indicates the keystore and the passphrase for the bank is loaded.

## IOBP-D-036

Extracting data from bank response in TransmitterUtil.extractResponse

### Description

Indicates Extracting data from bank response in TransmitterUtil.extractRespons given the key value to persist metadata in the transactions database.

## IOBP-D-037

Logging Message Header values

### Description

Indicates that the message headers are logged for debugging purposes.

## IOBP-D-038

[x] routing key `<key>`

### Description

Indicates the routing key of the messages pointing to the queue.

## IOBP-D-039

Now publish

### Description

Indicates that the message is published to the queue matching the routing key in the message.

## IOBP-D-040

Server `<rabbitserver>`

### Description

Indicates the rabbitmq server Server: `<rabbitserver>`.

## IOBP-D-041

Exchange `<exchange>`

### Description

Indicates the rabbitmq exchange Exchange: `<exchange>`.

## IOBP-D-042

Port `<port>`

### Description

Indicates the rabbitmq port Port: `<port>`.

## IOBP-D-043

InQueue `<inqueue>`

### Description

Indicates the rabbitmq queue InQueue: `<inqueue>` in which the returner is listening.