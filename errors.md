---

copyright:
  years: 2018
lastupdated: "2018-10-23"

---

<!-- Common attributes used in the template are defined as follows: -->
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}

# Error messages

## IOBP-E-001

[PaymentsService] (createPaymentSubmission) failed to retrieve the merchant redirect\_uri - unable to return to merchant page, error: <code>&lt;error&gt;</code> , <code>&lt;transactionId&gt;</code>

### Description

Error occured while retrieving the merchant redirect\_uri during payment submission - unable to return to merchant page, error: `<error>`, `<transactionId>`.

### Resolution

Create a support ticket to check the redirect_\uri correctness in the database, indicating details of the error such as http status code, error message and transactionId.
 
## IOBP-E-002

PaymentsService(createPaymentSubmission) payment submission failed. ERROR: `<error>`, `<transactionId>` 

### Description

Error occured while processing the payment submission request - payment submission failed. ERROR: `<error>`, `<transactionId>` .

### Resolution

Create a support ticket, indicating details of the error such as http status code, error message and transactionId.

## IOBP-E-003

=====> Error `<errorMsg>`, `<transactionId>` 

### Description

Error occured with the error messsage for the transactionId specified: `<errorMsg>`, `<transactionId>`.

### Resolution

Create a support ticket, indicating details of the error such as http status code, error message and transactionId.

## IOBP-E-004

Object error being returned. Should be string 

### Description

Error occured while processing a payment request - Object error being returned. Should be string.

### Resolution

Create a support ticket, indicating details of the error such as http status code, error message and transactionId.

## IOBP-E-005

`<error>`, `<transactionId>`

### Description

Displays the error for the transactionId `<error>`, `<transactionId>`.

### Resolution

Create a support ticket, indicating details of the error such as http status code, error message and transactionId.

## IOBP-E-006

Error during getBanks

### Description

Error occured during getBanks operation to get the list of banks from the database.

### Resolution

Create a support ticket, indicating details of the error such as http status code, error message and transactionId.

## IOBP-E-007

Unsupported query parameter

### Description

Error occured while processing the request - unsupported query parameter.

### Resolution

Check the request and its query parameters against the swagger and re-send the request.

## IOBP-E-008

[BANKS] (banksGet) nano error 

### Description

Error occured in the database during banksGet operation [BANKS] (banksGet) nano error.

### Resolution

Create a support ticket to check the banks database, indicating details of the error such as http status code, error message and transactionId.

## IOBP-E-009

[BANKS] (bankGetById) nano error 

### Description

Error occured in the database during bankGetById operation [BANKS] (bankGetById) nano error.

### Resolution

Create a support ticket to check the banks database, indicating details of the error such as http status code, error message and transactionId.

## IOBP-E-010

[BANKS] (banksGetByName) nano error

### Description

Error occured in the database during banksGetByName operation [BANKS] (banksGetByName) nano error.

### Resolution

Create a support ticket to check the banks database, indicating details of the err	or such as http status code, error message and transactionId.

## IOBP-E-011

[MERCHANTS] (merchantsGet) nano error

### Description

Error occured in the database during merchantsGet operation [MERCHANTS] (merchantsGet) nano error.

### Resolution

Create a support ticket to check the merchants database, indicating details of the error such as http status code, error message and transactionId.

## IOBP-E-012

[MERCHANTS] (merchantsGetById) nano error

### Description

Error occured in the database during merchantsGetById operation [MERCHANTS] (merchantsGetById) nano error

### Resolution

Create a support ticket to check the merchants database, indicating details of the error such as http status code, error message and transactionId. 

## IOBP-E-013

[MERCHANTS] (merchantsGetByName) nano error

### Description

Error occured in the database during merchantsGetByName operation [MERCHANTS] (merchantsGetByName) nano error.

### Resolution

Create a support ticket to check the merchants database, indicating details of the error such as http status code, error message and transactionId.

## IOBP-E-014

merchantId cannot be updated

### Description

Error occured while trying to update the merchant information in the database - merchantId cannot be updated.

### Resolution

Create a support ticket to check the merchants database, indicating details of the error such as http status code, error message and transactionId.

## IOBP-E-015

CouchDbManager.getBankInfo Error: Failed to find Bank for X-Fapi-Financial-Id[ `<fapiFinId>` ]

### Description

Error occured while trying to fetch the bank information from the `<db>` database given x-fapi-financial-id `<fapiId>` due to one of the following reasons 1. A db error occured during this operation or 2. The bank information matching the x-fapi-financial-id `<fapiId>` does not exist.

### Resolution

Create a support ticket to check the bank's database to check if the bank exists, indicating details of the error such as http status code, error message and transactionId, x-fapi-financial-id.

## IOBP-E-016

CouchDbManager.getBankURL Error: No target URL found for messageType=`<messageType>`

### Description

Error occured because there in no bank URL defined in the database for the given message type: `<messageType>`

### Resolution

Check the request to ensure it has one of the supported message types.

## IOBP-E-017

ICouchDbManager.putBankResponse.dbClient.find Error: Failed to find transaction for transactionId[`<transactionId>`]

### Description

Error occured while trying to fetch the transaction record from the `<db>` database given transactionId `<transactionId>` due to one of the following reasons: 1. A db error occured during this operation or 2. The transaction record matching the transactionId `<transactionId>` does not exist.

### Resolution 

Create a support ticket to check the transactions database to check if the transaction exists, indicating details of the error such as http status code, error message and transactionId.

## IOBP-E-018

CouchDbManager.putBankResponse.dbClient.update Error: Failed to update transaction for transactionId[`<transactionId>`]; Updated BankResponse: `<bankResponse>` 

### Description

Error occured while trying to execute the update operation for the transaction record found matching the transactionId `<transactionId>` in the transaction database.

### Resolution

Create a support ticket to check the database connection status and availability, indicating details of the error such as http status code, error message and transactionId.

## IOBP-E-019

CouchDbManager.putBankResponse Error: Failed to update bank response couchdb for transactionId[`<transactionId>`] 

### Description

Error occured during the process of retrieving and updating the transaction record for the given transactionId <transactionId> in the transactions database.

### Resolution

Create a support ticket to check the database connection status and availability, indicating details of the error such as http status code, error message and transactionId.

## IOBP-E-020

HttpClientErrorException in PSD2BankMessageHandler.sendMessage: status `<status>` calling `<httpMethod>` `<urlValue>`" 

### Description

Error occured when a HTTP request is sent to the bank and received a HTTP 4XX.

### Resolution

Validate the HTTP request format and create a support ticket to learn about the database and bank connectivity status.

## IOBP-E-021

RestClientException: calling `<httpMethod.name()`> `<urlValue>` 

### Description

Error occured when sending a HTTP rquest to the bank and HTTP client errors occur.

### Resolution

Validate the HTTP request format and create a support ticket to learn about the database and bank connectivity status.

## IOBP-E-022

Exception: calling `<httpMethod.name()`> `<urlValue>` 

### Description

Error occured while trying to send a HTTP request to the bank.

### Resolution

Validate the HTTP request format, headers and request body and retry the request.

## IOBP-E-023

Unsupported message type requested

### Description

Error occured while fetching the http method for the given message type because the message type is not supported.

### Resolution

Verify the HTTP request contains one of the supported message types and retry the request.

## IOBP-E-024

Init Status / Submit Status returned 404 

### Description

Error occured suring the Init Status / Submit Status - returned 404.

### Resolution

Create a support ticket to check the database for the bank URL correctness and the bank avaialbility, indicating details of the error such as http status code, error message and transactionId.

## IOBP-E-025

Incorrect response code detected

### Description

Error because incorrect response code detected.

### Resolution

Retry the request with the correct format for the HTTP request by validating it against the swagger.

## IOBP-E-026

Failed to connect to RabbitMQ 

### Description

Error occured because failed to connect to RabbitMQ.

### Resolution

Create a support ticket to check the status of the rabbitmq indicating details of the error, error message.

## IOBP-E-027

Failed to open a channel

### Description

Error occured because it failed to open a channel.

### Resolution

Create a support ticket to check the status of the rabbitmq indicating details of the error and error message.

## IOBP-E-028

Failed to declare an exchange

### Description

Error because - Failed to declare an exchange.

### Resolution

Create a support ticket to check the status of the rabbitmq indicating details of the error and error message.

## IOBP-E-029

Failed to bind a queue

### Description

Error because - Failed to bind a queue.

### Resolution

Create a support ticket to check the status of the rabbitmq indicating details of the error and error message.

## IOBP-E-030

Failed to register a consumer 

### Description

Error because - Failed to register a consumer.

### Resolution

Create a support ticket to check the status of the rabbitmq indicating details of the error and error message.

## IOBP-E-031

Failed to publish a message 

### Description

Error because - Failed to publish a message.

### Resolution

Create a support ticket to check the status of the rabbitmq indicating details of the error and error message.

## IOBP-E-032

Error in constructing the ignore message

### Description

Error in constructing the ignore message.

### Resolution

Create a support ticket to check the status of the http request. It is failing at the point of ignore message construction.

## IOBP-E-033

The transactionId is required but is null/empty 

### Description

Error occured during message validation because the transaction Id is null/empty.

### Resolution

Retry the request with a valid transaction Id.

## IOBP-E-034

The messagetype is null/empty

### Description

Error occured during message validation because the messagetype is null/empty.

### Resolution

Retry the request with a valid  messagetype.

## IOBP-E-035

The bankid is null/empty

### Description

Error occured during message validation because the bankid is null/empty.

### Resolution

Retry the request with a valid bankid.

## IOBP-E-036

The auth code is required - cannot be null/empty 

### Description

Error occured during message validation because the auth code is required - cannot be null/empty.

### Resolution

Create a support ticket to investigate the reason for the auth code to be null/empty with details indicating the http status code, error msg and the http request information.

## IOBP-E-037

The ignore header is null/empty

### Description

Error occured during message validation because the ignore header is null/empty.

### Resolution

Retry the request with a valid ignore header.

## IOBP-E-038

The Message is marked as Ignored

### Description

Error occured during message validation because the message is marked as Ignored.

### Resolution

Retry the request with all the required message headers.

## IOBP-E-039

The MessageHeaders is missing, `<missingHeadersList>`

### Description

Error occured during message validation because the MessageHeaders is missing, `<missingHeadersList>`.

### Resolution

Retry the request with all the required message headers.

## IOBP-E-040

The MessageHeaders is missing, `<missingHeadersList>`

### Description

Error occured during message validation because the MessageHeaders is missing, `<missingHeadersList>`.

### Resolution

Retry the request with all the required message header.

## IOBP-E-041

Failed while creating banks 

### Description

Error occured because the operation failed while creating banks. 

### Resolution

Validate the create request for correctness of the bank json and create a support ticket to investigate why the db operation failed while creating banks with http status code, error msg, and the http request information.

## IOBP-E-042

Failed while deleting banks for bankId: `<bankId>`

### Description

Error occured because the operation Failed while deleting banks for bankId: `<bankId>`.

### Resolution

Validate the delete request for correctness of bankId and create a support ticket to investigate why the db operation failed while deleting banks with http status code, error msg, and the http request information.

## IOBP-E-043

Failed while getting banks by name:`<bankName>`

### Description

Error occured because the operation Failed while getting banks by name:`<bankName>`

### Resolution

Validate the delete request for correctness of bankName and create a support ticket to investigate why the db operation failed while deleting banks with http status code, error msg, and the http request information.

## IOBP-E-044

Failed while getting banks 

### Description

Error occured because the operation Failed while getting banks.

### Resolution

Validate the get request for correctness and create a support ticket to investigate why the db operation failed while getting banks with http status code, error msg, and the http request information.

## IOBP-E-045

Failed while getting banks by Id:`<bankId>` 

### Description

Error occured because the operation failed while getting banks by Id:`<bankId>`.

### Resolution

Validate the get request for correctness for bankId and create a support ticket to investigate why the db operation failed while getting banks with http status code, error msg, and the http request information.

## IOBP-E-046

Failed while updating banks `<bankId>`

### Description

Error occured because the operation failed while updating banks `<bankId>`.

### Resolution

Validate the update request for correctness for bankId and create a support ticket to investigate why the db operation failed while updating banks with http status code, error msg, and the http request information.

## IOBP-E-047

Failed while creating merchants

### Description

Error occured because the operation Failed while creating merchants.

### Resolution

Validate the get request for correctness of merchant json and create a support ticket to investigate why the db operation failed while creating merchant with http status code, error msg, and the http request information.

## IOBP-E-048

Failed while deleting merchants:`<merchantId>`

### Description

Error occured because the operation failed while deleting merchants:`<merchantId>`.

### Resolution

Validate the get request for correctness of merchantId and create a support ticket to investigate why the db operation failed while deleting merchant with http status code, error msg, and the http request information.

## IOBP-E-049

Failed while getting merchants 

### Description

Error occured because the operation failed while getting merchants.

### Resolution

Validate the get request for correctness and create a support ticket to investigate why the db operation failed while retrieving merchant with http status code, error msg, and the http request information.

## IOBP-E-050

Failed while getting merchants by merchant name:`<merchantName>`

### Description

Error occured because the operation failed while getting merchants by merchant name:`<merchantName>`.

### Resolution

Validate the get request for correctness of merchant name and create a support ticket to investigate why the db operation failed while retrieving merchant with http status code, error msg, and the http request information.

## IOBP-E-051

Failed while getting merchants by merchant id:`<merchantName>`

### Description

Error occured because the operation failed while getting merchants by merchant id:`<merchantName>`.

### Resolution

Validate the get request for correctness of merchant Id and create a support ticket to investigate why the db operation failed while retrieving merchant with http status code, error msg, and the http request information.

## IOBP-E-052

Failed while updating merchants :`<merchantName>` 

### Description

Error occured because the operation failed while updating merchants :`<merchantName>`

### Resolution

Validate the update request for correctness and create a support ticket to investigate why the db operation failed while retrieving merchant with http status code, error msg, and the http request information.

## IOBP-E-053

Unable to retrieve the bank information

### Description

Error occured while trying to fetch the bank information from the `<db>` database given x-fapi-financial-id `<fapiId>` due to one of the following reasons: 1. A db occured during this operation or 2. The bank information matching the x-fapi-financial-id `<fapiId>` does not exist.

### Resolution

Create the support ticket to check the db connectivity status and availability with details such as http status code, error msg description and x-fapi-financial-id.

## IOBP-E-054

Unable to get the declared constructor of the handler class 

### Description

Error occured while trying to find the constructor of the bank message handler class.

### Resolution

Create a support ticket to validate the correctness of the handlerClass name in the banks database.

## IOBP-E-055

Access denied to the package of the handler class

### Description

Error occured while loading the bank messsage handler class because the SecurityManager denies access to the package of this class.

### Resolution

Create a support ticket to validate the correctness of the handlerClass name in the banks database.

## IOBP-E-056

Unable to instantiate the handler class object

### Description

Error occured while instantiating the dynamically loaded bank message handler class because it is an abstract class.

### Resolution

Create a support ticket to validate the correctness of the handlerClass name in the banks database.

## IOBP-E-057

Unable to access the handler class object's constructor

### Description

Error occured while accessing the constructor of the dynamically loaded bank handler class.

### Resolution

Create a support ticket to validate the correctness of the handlerClass name in the banks database.

## IOBP-E-058

Illegal parameters send to the handler class object

### Description

Error occured because illegal parameters that do not match the number or type of arguments sent to the bank message handler constructor.

### Resolution

Create a support ticket to validate the correctness of the handlerClass name in the banks database.

## IOBP-E-059

Error from the handler class constructor

### Description

Error thrown from the bank message handler class constructor.

### Resolution

Create a support ticket to validate the correctness of the handlerClass name in the banks database.

## IOBP-E-060

Invalid handler class 

### Description

Error occured while trying to dynamically load the bank message handler class for a given invalid (null or empty) handler class name.

### Resolution

Create a support ticket to validate the correctness of the handlerClass name in the banks database.

## IOBP-E-061

Exception occured while loading the keystore and SSLContext in SecureSocketsManager.getSSLContext

### Description

Error occured in loading the keystore and creating the SSLContext for the bank identified by the given bankId.

### Resolution

Create the support ticket to validate the correctness of the keystore for the given bankId.

## IOBP-E-062

Invalid Bank Info : x-fapi-financial-id is missing

### Description

Error occured because invalid bank info is present in the database without x-fapi-financial id.

### Resolution

Create the support ticket to validate the correctness of the bank info in the database with the correct x-fapi-financial-id.

## IOBP-E-063

The keystore/passphrase is not defined 

### Description

Error occured while fetching the keystore/passphrase and it is not defined.

### Resolution

Ensure to set the correct keystore and passphrase as environment variables and retry the request.

## IOBP-E-064

Message Transformation Failure `<exception>`

### Description

Error occured while processing the message -  message validation failure occured.

### Resolution

Retry the request after validating the correctness of the message format.

## IOBP-E-065

The message is invalid

### Description

Error occured while processing the message - the message(payload) is invalid.

### Resolution

Retry the request after validating the correctness of the payload.

## IOBP-E-066

Unknown payload type 

### Description

Error occured while processing the message - unknown payload type.

### Resolution

Retry the request after validating the correctness of the payload type.

## IOBP-E-000P

ERROR_CODE_INVALID_MESSAGE 

### Description

Error occured because message is invalid.

### Resolution

Validate the correctness of message format and retry the request.

## IOBP-E-000Q

ERROR_CODE_INVALID_TRANSACTIONID

### Description

Error occured because the message has invalid transactionId.

### Resolution

Validate the correctness of transactionId and retry the request.

## IOBP-E-000R

ERROR_CODE_INVALID_MESSAGE_TYPE 

### Description

Error occured because the message type is invalid.

### Resolution

Validate the correctness of message type and retry the request.

## IOBP-E-000S

ERROR_CODE_INVALID_BANKID 

### Description

Error occured because the bank id is invalid.

### Resolution

Validate the correctness of bankId and retry the request.

## IOBP-E-000T

ERROR_CODE_IGNORE_SET 

### Description

Error occured because the message has ignore header set.

### Resolution

Validate the correctness of ignore header and retry the request.

## IOBP-E-000U

ERROR_CODE_INVALID_PAYLOAD_TYPE

### Description

Error occured becuase the payload type is invalid.

### Resolution

Validate the correctness of payload type and retry the request.

## IOBP-E-000V

ERROR_CODE_INVALID_MESSAGE_HEADERS

### Description

Error occured because the message headers are invalid.

### Resolution

Validate the correctness of message headers and retry the request.

## IOBP-E-0500

ERROR_CODE_BACKEND_EXCEPTION

### Description

Error occured during message processing in the backend and a bankend exception is thrown.

### Resolution

Create a support ticket to check the status of the backend with details of the error message, http status code, and the http request information.

## IOBP-E-0401

ERROR_CODE_INVALID_AUTHCODE

### Description

Error occured because the auth code is invalid.

### Resolution

Create a support ticket to check the validation of the auth code, with details of the http status, error msg, transactionId, and the http request information.
