---

copyright:
  years: 2018
lastupdated: "2018-10-14"

---

<!-- Common attributes used in the template are defined as follows: -->
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}

# Debug messages

| Number | Message | Description |
| :--- | :--- | :--- |
| IOBP-D-001 | CouchDbManager.getBankURL for messageType {} `<messageType>` | Fetching the bank URL from the database given the message type: `<messageType>` |
| IOBP-D-002 | Sending to {}, `<urlValue>` | Indicates that the request is being sent to bank, `<urlValue>` |
| IOBP-D-003 | CouchDbManager.putBankResponse for transactionId, `<transactionId>` | Updates the transactions database with the bank response metadata |
| IOBP-D-004 | CouchDbManager.putBankResponse Transaction Found: `<json>.toString()` | Indicates the transaction with the given transationId is found |
| IOBP-D-005 | CouchDbManager.putBankResponse Transaction Found: `<json>.toString()` | Indicates the transaction with the given transationId is found |
| IOBP-D-006 | CouchDbManager.getCouchDbProperties for database: `<db>` | Fetching the couchdb properties to connect to database: `<db>` |
| IOBP-D-007 | =====>CouchDbManager.getCouchDbProperties properties for database [`<db>`], host [`<host>`], port [`<port>`], username [`<username>`] | Logging the CouchDb properties for database [`<db>`], host [`<host>`], port [`<port>`], username [`<username>`] |
| IOBP-D-008 | CouchDbManager.getBankInfo for x-fapi-financial-id: `<fapiFinId>` | Calling CouchDbManager.getBankInfo for given x-fapi-financial-id: `<fapiFinId>` to retrieve the bank information |
| IOBP-D-009 | returnString {} , `<returnString>` | Logging the return string |
| IOBP-D-010 | Message sent and waiting for reply | Indicates that the Message is sent and waiting for reply from the bank |
| IOBP-D-011 | Reponse : `<responseEntity.getStatusCode()>` -  `<responseEntity.getBody()>` | Logging the metadata of the response for debugging purpose |
| IOBP-D-012 | Now publish | Indicates that the component is now publishing messages to the queue |
| IOBP-D-013 | [*] Waiting for messages. To exit, press CTRL+C | Indicates the returner is connected to rabbitmq and waiting to consume messages |
| IOBP-D-014 | Payments.getBanks | Request processing to get the list of banks has started |
| IOBP-D-015 | =====> Payments.getBanks.end | Request processing to get the list of banks has ended |
| IOBP-D-016 | =====> Resolve Banks | Indicates the list of banks retrieved from the database |
| IOBP-D-017 | [PaymentsService] (createPaymentSubmission) payment submission started, `<transactionId>` | Indicates [PaymentsService] (createPaymentSubmission) payment submission started, `<transactionId>` |
| IOBP-D-018 | [PaymentsService] (createPaymentSubmission) payment submission completed successfully, `<transactionId>` | Indicates [PaymentsService] (createPaymentSubmission) payment submission completed successfully, `<transactionId>` |
| IOBP-D-019 | json[code], messageType, transactionId | Indicates the json[code], messageType, transactionId for the current request being processed |
| IOBP-D-020 | `<messageType>` + ended with ERROR, `<transactionId>` | Indicates the request processing for `<messageType>` + ended with ERROR, assigned with `<transactionId>` |
| IOBP-D-021 | Payment init started, `<transactionId>` | Indicates the request processing got payment init started, assigned with `<transactionId>` |
| IOBP-D-022 | Sending response `<%s>`, JSON.stringify( response ), `<transactionId>` | Indicates the sending response `<%s>`, JSON.stringify( response ), `<transactionId>` |
| IOBP-D-023 | Redirect\_url: `<url>`, `<transactionId>` | Indicates the redirect\_url: `<url>`, for the transaction `<transactionId>` |
| IOBP-D-024 |`<messageType>` ended, `<transactionId>` | Indicates the request processing for `<messageType>` ended, assigned with `<transactionId>` |
| IOBP-D-025 |Connected to the database: `<db>` | Connected successfully to the backend database: `<db>` |
| IOBP-D-026 | CouchDbManager.getBankInfo for x-fapi-financial-id: `<fapiId>` | Gets the bank information given the x-fapi-financial-id: `<fapiId>` |
| IOBP-D-027 | Bank information for the given X-FAPI-FINANCIAL\_ID `<fapiId>` does not exist | The database does not contain information matching the given x-fapi-financial-id: `<fapiId>` |
| IOBP-D-028 | Connected to the transactions database in Couchdb | Indicates that the connection to the couchdb db is successful |
| IOBP-D-029 | CouchDbManager.putBankResponse Transaction found for the transactionId | Indicates the transaction record matching the transactionId `<transactionId>` is found in the transactions database |
| IOBP-D-030 | Updated bank response to the transaction history database | Indicates the transaction record matching the transactionId `<transactionId>` is updated with the bank response metadata |
| IOBP-D-031 | Parsing the http headers | Parsing the http headers to send it as part of the http request to the bank |
| IOBP-D-032 | PSD2BankMessageHandler.sendMessage(), response received from the bank | Indicates that an http response is received from the bank |
| IOBP-D-033 | SecureSocketManager.getRestTemplate() is called | SecureSocketManager.getRestTemplate() is called to assemble the http request to be sent to the bank |
| IOBP-D-034 | SecureSocketsManager.getSSLContext for bank: `<bankId>` | SecureSocketsManager.getSSLContext for bank is created by loading the corresponding keystore given the bankId |
| IOBP-D-035 | SecureSocketsManager.getSSLContext passphrase: `<passphrase>`,keystore: `<keystore>` | Indicates the keystore and the passphrase for the bank is loaded |
| IOBP-D-036 | Extracting data from bank response in TransmitterUtil.extractResponse | Indicates Extracting data from bank response in TransmitterUtil.extractRespons given the key value to persist metadata in the transactions database |
| IOBP-D-037 | Logging Message Header values | Indicates that the message headers are logged for debugging purpose |
| IOBP-D-038 | [x] routing key `<key>` | Indicates the routing key of the messages pointing to the queue |
| IOBP-D-039 | Now publish | Indicates that the message is published to the queue matching the routing key in the message |
| IOBP-D-040 | Server: `<rabbitserver>` | Indicates the rabbitmq server Server: `<rabbitserver>` |
| IOBP-D-041 | Exchange: `<exchange>` | Indicates the rabbitmq exchange Exchange: `<exchange>` |
| IOBP-D-041 | Port: `<port>` | Indicates the rabbitmq port Port: `<port>` |
| IOBP-D-043 | InQueue: `<inqueue>` | Indicates the rabbitmq queue InQueue: `<inqueue>` in which the returner is listening |