---

copyright:
  years: 2018
lastupdated: "2018-10-15"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}

# Getting started with IBM Open Banking Platform
{{site.data.keyword.iobp_full}} is a software suite that accelerates a bank's transformation to a platform economy. 
In this getting started tutorial, you get the list of ASPSPs, set up a single payment, and get the payment status.

## Before you begin
{: #prereqs}
The following steps show you how to invoke API methods for the {{site.data.keyword.iobp_short}} service. To use the {{site.data.keyword.iobp_short}} REST API, it is important that you understand the basics of RESTful web services and JSON representations.

You must install cURL before you can use the steps in this tutorial.

## Step 1: Getting your credentials

1. Log in to IBM API Connect.
2. Click **Apps**.
3. Click **Create new App**.
4. To register the application, enter the title of your application and click **Submit**.
5. Click **Show Client Secret** and copy the Client Secret into a text file to keep it to use later in this tutorial.
6. Scroll down until you see the Client ID. Click **Show** next to the Client ID and copy it into the same file you used in step 5.  
7. Click **API Products**.
8. Click the Open Banking API.
9. Click **Subscribe**.
10. In the dialog box, select the application that you created in steps 3 - 4 and click **Subscribe**.

To use the following examples, replace &lt;client-id&gt; and &lt;client-secret&gt; with the values you acquired in this step.

## Step 2: Get a list of ASPSPs

A payment initiation begins with a PSU consenting to a payment being made from an ASPSP. The request is sent to the TPP.

This operation returns a list of ASPSPs from the TPP so that this list can be provided to the PSU. Getting the list of ASPSPs allows you to authorize your consent.

The following is an example of a GET /banks request:
```
curl -X GET -H "x-ibm-client-id: <client-id>" -H "x-ibm-client-secret: <client-secret>" -H "Cache-Control: no-cache"  https://<hostname>/open-banking/v1.1/banks
```
{:codeblock}

The service returns a response that contains the name, country code, and status of the ASPSP. The following is an example of the GET/banks response:

```
[
    {
        "x-fapi-financial-id": "4444",
        "name": "Bluebee Bank",
        "sortCode": "xyz",
        "BICFI": "be2e44b06b34"
    },
    {
        "x-fapi-financial-id": "0015800001041REAAY",
        "name": "Forgerock",
        "sortCode": "xyz",
        "BICFI": "be2e44b06b3400"
    }
]
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
        "Amount": "165.88",
        "Currency": "GBP"
      },
      "CreditorAccount": {
        "SchemeName": "SortCodeAccountNumber",
        "Identification": "93960176796058",
        "Name": "ACME Inc",
        "SecondaryIdentification": "0002"
      },
      "DebtorAccount": {
        "SchemeName": "SortCodeAccountNumber",
        "Identification": "93960176796058",
        "Name": "PSU1",
        "SecondaryIdentification": "0001"
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
      "StreetName": "astor pl",
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
curl -X POST -H "x-ibm-client-id: <client-id>" -H "x-ibm-client-secret: <client-secret>" -H "Accept: application/json" -H "Authorization: Bearer" -H "Cache-Control: no-cache" -H "Content-Type: application/json" -H "merchantId: 1234" -H "x-fapi-customer-ip-address: 104.25.212.99" -H "x-fapi-customer-last-logged-time: Sun, 10 Sep 2017 19:43:31 UTC" -H "x-fapi-financial-id: 0015800001041REAAY" -H "x-idempotency-key: FRESCO.21302.GFX.20" -H "x-fapi-interaction-id: 93bac548-d2de-4546-b106-880a5018460d" -d @create_payment.json  https://<hostname>/open-banking/v1.1/payments
```
{:codeblock}

The following is the response to a successful request:
```
{
    "Data": {
        "PaymentId": "Pe862bf40-715d-43f4-88a6-d60e26e12924",
        "Status": "AcceptedTechnicalValidation",
        "CreationDateTime": "2018-10-11T18:59:24+00:00",
        "Initiation": {
            "InstructionIdentification": "dc087160cd87-11e8-95ad-7f3755d1d26a",
            "EndToEndIdentification": "FRESCO.21302.GFX.20",
            "InstructedAmount": {
                "Amount": "165.88",
                "Currency": "GBP"
            },
            "DebtorAccount": {
                "SchemeName": "SortCodeAccountNumber",
                "Identification": "93960176796058",
                "Name": "PSU1",
                "SecondaryIdentification": "0001"
            },
            "CreditorAccount": {
                "SchemeName": "SortCodeAccountNumber",
                "Identification": "93960176796058",
                "Name": "ACME Inc",
                "SecondaryIdentification": "0002"
            },
            "RemittanceInformation": {
                "Unstructured": "Internal ops code 5120101",
                "Reference": "FRESCO-101"
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
            "StreetName": "astor pl",
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

## Step 4: Get payment status

This operation specifies the PaymentId, returned by creating the payment in Step 3, in the path and returns the payment with that ID.

To get the status of the payment, use the GET /payments/{PaymentId} as in the following example:
```
curl -X GET -H "x-ibm-client-id: <client-id>" -H "x-ibm-client-secret: <client-secret>" -H "Accept: application/json" -H "Authorization: Bearer" -H "Cache-Control: no-cache" -H "Content-Type: application/json" -H "merchantId: 1234"  -H "x-fapi-customer-ip-address: 104.25.212.99" -H "x-fapi-customer-last-logged-time: Sun, 10 Sep 2017 19:43:31 UTC" -H "x-fapi-financial-id: 0015800001041REAAY" -H "x-idempotency-key: FRESCO.21302.GFX.20" -H "x-fapi-interaction-id: 93bac548-d2de-4546-b106-880a5018460d" https://<hostname>/open-banking/v1.1/payments/Pe862bf40-715d-43f4-88a6-d60e26e12924 
```
{:codeblock}

The following is the response to a successful request:
```
{
    "Data": {
        "PaymentId": "Pe862bf40-715d-43f4-88a6-d60e26e12924",
        "Status": "AcceptedTechnicalValidation",
        "CreationDateTime": "2018-10-11T18:59:24+00:00",
        "Initiation": {
            "InstructionIdentification": "dc087160cd87-11e8-95ad-7f3755d1d26a",
            "EndToEndIdentification": "FRESCO.21302.GFX.20",
            "InstructedAmount": {
                "Amount": "165.88",
                "Currency": "GBP"
            },
            "DebtorAccount": {
                "SchemeName": "SortCodeAccountNumber",
                "Identification": "93960176796058",
                "Name": "PSU1",
                "SecondaryIdentification": "0001"
            },
            "CreditorAccount": {
                "SchemeName": "SortCodeAccountNumber",
                "Identification": "93960176796058",
                "Name": "ACME Inc",
                "SecondaryIdentification": "0002"
            },
            "RemittanceInformation": {
                "Unstructured": "Internal ops code 5120101",
                "Reference": "FRESCO-101"
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
            "StreetName": "astor pl",
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
