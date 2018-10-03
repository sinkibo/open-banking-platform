---

copyright:
  years: 2018
lastupdated: "2018-09-26"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}

# Getting started with IBM Open Banking Platform
{{site.data.keyword.iobp_full}} is a software suite that accelerates a bank’s transformation to a platform economy. 
In this getting started tutorial, you get the list of ASPSPs, set up a single payment, and get the payment status.

## Before you begin
{: #prereqs}
The following steps show you how to invoke API methods for the {{site.data.keyword.iobp_short}} service. To use the {{site.data.keyword.iobp_short}} REST API, it is important that you understand the basics of RESTful web services and JSON representations.

You must install cURL before you can use the service.

These endpoints are protected by OAuth 2.0. As a merchant, after you onboard with the {{site.data.keyword.iobp_short}}, you will use your Client ID and Client Secret to request an access token, which you can then use to make calls to the endpoints.

## Step 1: Getting your credentials

1. Create an instance of the service.
2. Review the service instance access credentials, similar to the following example:
```
{
  "X-IBM-Client-Id": "<client-id>",
  "X-IBM-Client-Secret": "<client-secret>"
}
```

To use the following examples, replace &lt;client-id&gt; and &lt;client-secret&gt; with the values you acquired in this step.

## Step 2: Get a list of ASPSPs

A payment initiation begins with a PSU consenting to a payment being made from an ASPSP. The request is sent to the TPP.

This operation returns a list of ASPSPs from the TPP so that this list can be provided to the PSU. Getting the list of ASPSPs allows you to authorize your consent.

The following is an example of a GET /banks request:
```
curl -X GET -H "X-IBM-Client-Id: <client-id>" -H "X-IBM-Client-Secret: <client-secret>" -H "Cache-Control: no-cache"  https://api.us.apiconnect.ibmcloud.com/devikathapar1-test/merchants/open-banking/v1.1/banks
```
{:codeblock}

The service returns a response that contains the name, country code, and status of the ASPSP. The following is an example of the GET/banks response:

```
insert curl example
```
{:codeblock}

## Step 3: Create a payment

This operation connects the TPP to the ASPSP that services the customer's payment account and creates a new payments resource. This informs the ASPSP that one of its customers intends to make a payment. The ASPSP responds with an identifier, status, and other data for the resource. 

Before using the example in this step, save the following JSON code in a file named create_payment.json:

```
{
  "Data": {
    "Initiation": {
      "EndToEndIdentification": "FRESCO.21302.GFX.20",
      "InstructedAmount": {
        "Amount": "165.00",
        "Currency": "GBP"
      },
      "CreditorAccount": {
        "SchemeName": "SortCodeAccountNumber",
        "Identification": "08080021325698",
        "Name": "ACME Inc",
        "SecondaryIdentification": "0002"
      },
      "RemittanceInformation": {
        "Reference": "FRESCO-101",
        "Unstructured": "Internal ops code 5120101"
      }
    }
  },
  "Risk": {
    "PaymentContextCode": "EcommerceGoods",
    "MerchantCategoryCode": "5967",
    "MerchantCustomerIdentification": "053598653254",
    "DeliveryAddress": {
      "AddressLine": [
        "Flat 7",
        "Acacia Lodge"
      ],
      "StreetName": "Acacia Avenue",
      "BuildingNumber": "27",
      "PostCode": "GU31 2ZZ",
      "TownName": "Sparsholt",
      "CountrySubDivision": [
        "Wessex"
      ],
      "Country": "UK"
    }
  }
} 
```
{:codeblock}

To create a payment, use the POST /payments request as in the following example:

```
curl -X POST -H "X-IBM-Client-Id: <client-id>" -H "X-IBM-Client-Secret: <client-secret>" -H "Accept: application/json" -H "Cache-Control: no-cache" -H "Content-Type: application/json" -H "merchantId: 1234" -H "x-fapi-financial-id: 0015800001041REAAY" -H "x-idempotency-key: FRESCO.21302.GFX.20" -d @create_payment.json  https://api.us.apiconnect.ibmcloud.com/devikathapar1-test/merchants/open-banking/v1.1/payments
```
{:codeblock}

The following is the response to a successful request:
```
insert example response here
```
{:codeblock}

## Step 4: Get payment status

This operation specifies the PaymentId in the path and returns the payment with that ID. 

To get the status of the payment, use the GET /payments/{PaymentId} as in the following example:
```
curl -X GET -H "X-IBM-Client-Id: <client-id>" -H "X-IBM-Client-Secret: <client-secret>" -H "Accept: application/json" -H "Cache-Control: no-cache" -H "Content-Type: application/json" -H "merchantId: 1234" -H "x-fapi-customer-ip-address: 104.25.212.99" -H "x-fapi-customer-last-logged-time: Sun, 10 Sep 2017 19:43:31 UTC" -H "x-fapi-financial-id: 0015800001041REAAY" -H "x-fapi-interaction-id: 93bac548-d2de-4546-b106-880a5018460d" -H "x-idempotency-key: FRESCO.21302.GFX.20" https://api.us.apiconnect.ibmcloud.com/devikathapar1-test/merchants/open-banking/v1.1/payments/Pa87f8009-e881-47e7-83f6-709eb224220d 
```
{:codeblock}

The following is the response to a successful request:
```
insert example response here
```
{:codeblock}
