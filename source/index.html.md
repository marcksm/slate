---
title: API Reference
language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:

search: true
---

# Introduction

Welcome to the Bloom API!

# Authentication


# Buyers

## Create a Buyers
### HTTP Request
`POST http://localhost:3000/v1/buyers`

This endpoint creates a buyer.

```shell
curl -X POST -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/buyers" \
  -d '{"email":"teste@teste.com", "cpf":"27546072000", "first_name": "João", "last_name": "Testador"}'
```
Parameter | Description                              | Required? | Observation
--------- | -----------------------------------------| --------- | -----
email     | string - email of the buyer              | yes       | email must be a registered bloom user
cpf       | string - cpf of the buyer                | yes       | CPF must be unique
first_name| string - first_name of the buyer         | yes       |
last_name | string - last_name of the buyer          | yes       |
description | string - description of the buyer      | no        |
phone_number | string - phone_number of the buyer    | no        |
birthdate | string - birthdate of the buyer          | no        | format YYYY-mm-dd
address | string - address of the buyer              | no        |
email_optin | boolean email_optin of the buyer       | no        | wants to receive email, default: false
sms_optin | boolean sms_optin of the buyer           | no        | wants to receive sms, default: false
payment_methods | list payment_methods of the buyer  | no        | object "card" or "bankaccount"
default_debit | The default_debit of the buyer       | no        |
default_credit | The default_credit of the buyer     | no        |
twitter | The twitter of the buyer                   | no        |
facebook | The facebook of the buyer                 | no        |

> The above command returns JSON structured like this:

```json
  {
    "id": "64428de9655a4694bb3ff5e81d5af546",
    "status": "active",
    "resource": "buyer",
    "account_balance": "0.00",
    "current_balance": "0.00",
    "first_name": "João",
    "last_name": "Testador",
    "taxpayer_id": "27546072000",
    "description": null,
    "email": "teste@teste.com",
    "phone_number": null,
    "facebook": null,
    "twitter": null,
    "address": {
        "line1": null,
        "line2": null,
        "line3": null,
        "neighborhood": null,
        "city": null,
        "state": null,
        "postal_code": null,
        "country_code": null
    },
    "delinquent": false,
    "payment_methods": null,
    "default_debit": null,
    "default_credit": null,
    "default_receipt_delivery_method": null,
    "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/buyers/64428de9655a4694bb3ff5e81d5af546",
    "metadata": {},
    "created_at": "2018-08-27T12:52:59+00:00",
    "updated_at": "2018-08-27T12:52:59+00:00"
  }
```

## Update a Buyers
### HTTP Request
`PUT http://localhost:3000/v1/buyers/:buyer_id`

This endpoint creates a buyer.

```shell
curl -X PUT -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/buyers/64428de9655a4694bb3ff5e81d5af546" \
  -d '{"email":"novo@teste.com", "first_name": "José"}'
```
Parameter | Description                              | Required? | Observation
--------- | -----------------------------------------| --------- | -----
buyer_id  | string - buyer_id of the buyer           | yes       |
email     | string - email of the buyer              | no        | email must be a registered bloom user
first_name| string - first_name of the buyer         | no        |
last_name | string - last_name of the buyer          | no        |
description | string - description of the buyer      | no        |
phone_number | string - phone_number of the buyer    | no        |
birthdate | string - birthdate of the buyer          | no        | format YYYY-mm-dd
address | string - address of the buyer              | no        |
email_optin | boolean email_optin of the buyer       | no        | wants to receive email, default: false
sms_optin | boolean sms_optin of the buyer           | no        | wants to receive sms, default: false
payment_methods | list payment_methods of the buyer  | no        | object "card" or "bankaccount"
default_debit | The default_debit of the buyer       | no        |
default_credit | The default_credit of the buyer     | no        |
twitter | The twitter of the buyer                   | no        |
facebook | The facebook of the buyer                 | no        |

> The above command returns JSON structured like this:

```json
  {
    "id": "64428de9655a4694bb3ff5e81d5af546",
    "status": "active",
    "resource": "buyer",
    "account_balance": "0.00",
    "current_balance": "0.00",
    "first_name": "José",
    "last_name": "Testador",
    "taxpayer_id": "27546072000",
    "description": null,
    "email": "novo@teste.com",
    "phone_number": null,
    "facebook": null,
    "twitter": null,
    "address": {
        "line1": null,
        "line2": null,
        "line3": null,
        "neighborhood": null,
        "city": null,
        "state": null,
        "postal_code": null,
        "country_code": null
    },
    "delinquent": false,
    "payment_methods": null,
    "default_debit": null,
    "default_credit": null,
    "default_receipt_delivery_method": null,
    "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/buyers/64428de9655a4694bb3ff5e81d5af546",
    "metadata": {},
    "created_at": "2018-08-27T12:52:59+00:00",
    "updated_at": "2018-08-27T12:52:59+00:00"
  }
```

## Get All Buyers

```shell
curl "http://localhost:3000/v1/buyers"

```

> The above command returns JSON structured like this:

```json
{
  "resource": "list",
  "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/buyers?limit=100&offset=0",
  "items": [
      {
          "id": "ce671146c66448f9b0efbdd16b999b07",
          "status": "active",
          "resource": "buyer",
          "account_balance": "0.00",
          "current_balance": "0.00",
          "first_name": "JOhn",
          "last_name": "dasdsadas",
          "taxpayer_id": "27546072000",
          "description": null,
          "email": "teste@teste.com",
          "phone_number": "321321321",
          "facebook": null,
          "twitter": null,
          "address": {
              "line1": null,
              "line2": null,
              "line3": null,
              "neighborhood": null,
              "city": null,
              "state": null,
              "postal_code": null,
              "country_code": null
          },
          "delinquent": false,
          "payment_methods": null,
          "default_debit": null,
          "default_credit": null,
          "default_receipt_delivery_method": null,
          "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/buyers/ce671146c66448f9b0efbdd16b999b07",
          "metadata": {
              "twitter.id": "",
              "facebook.user_id": "",
              "my-own-customer-id": ""
          },
          "created_at": "2018-08-23T15:21:21+00:00",
          "updated_at": "2018-08-23T15:21:21+00:00"
      },
      {
          "id": "5835dc2d5fed40509c035f017e4f487c",
          "status": "active",
          "resource": "buyer",
          "account_balance": "0.00",
          "current_balance": "0.00",
          "first_name": "JOhn",
          "last_name": "dasdsadas",
          "taxpayer_id": "90817804099",
          "description": null,
          "email": "dsadasdasdasdasbla@bla.com",
          "phone_number": "321321321",
          "facebook": null,
          "twitter": null,
          "address": {
              "line1": null,
              "line2": null,
              "line3": null,
              "neighborhood": null,
              "city": null,
              "state": null,
              "postal_code": null,
              "country_code": null
          },
          "delinquent": false,
          "payment_methods": null,
          "default_debit": null,
          "default_credit": null,
          "default_receipt_delivery_method": null,
          "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/buyers/5835dc2d5fed40509c035f017e4f487c",
          "metadata": {
              "twitter.id": "",
              "facebook.user_id": "",
              "my-own-customer-id": ""
          },
          "created_at": "2018-08-23T15:20:45+00:00",
          "updated_at": "2018-08-23T15:20:45+00:00"
      },
  ],
  "limit": 100,
  "offset": 0,
  "has_more": false,
  "query_count": 39,
  "total": 2
}
```

This endpoint retrieves all buyers.

### HTTP Request

`GET http://localhost:3000/v1/buyers`



## Get a Specific Buyer


```shell
curl "http://localhost:3000/v1/buyers/ce671146c66448f9b0efbdd16b999b07"

```


> The above command returns JSON structured like this:

```json
{
  "id": "ce671146c66448f9b0efbdd16b999b07",
  "status": "active",
  "resource": "buyer",
  "account_balance": "0.00",
  "current_balance": "0.00",
  "first_name": "JOhn",
  "last_name": "dasdsadas",
  "taxpayer_id": "27546072000",
  "description": null,
  "email": "teste@teste.com",
  "phone_number": "321321321",
  "facebook": null,
  "twitter": null,
  "address": {
      "line1": null,
      "line2": null,
      "line3": null,
      "neighborhood": null,
      "city": null,
      "state": null,
      "postal_code": null,
      "country_code": null
  },
  "delinquent": false,
  "payment_methods": null,
  "default_debit": null,
  "default_credit": null,
  "default_receipt_delivery_method": null,
  "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/buyers/ce671146c66448f9b0efbdd16b999b07",
  "metadata": {
      "twitter.id": "",
      "facebook.user_id": "",
      "my-own-customer-id": ""
  },
  "created_at": "2018-08-23T15:21:21+00:00",
  "updated_at": "2018-08-23T15:21:21+00:00"
}
```

This endpoint retrieves a specific buyer.


### HTTP Request

`GET http://localhost:3000/v1/buyers/:buyer_id`

### URL Parameters

Parameter | Description
--------- | -----------
buyer_id | The ID of the buyer to retrieve

## Delete a Specific Buyer


```shell
curl "http://localhost:3000/v1/buyers/ce671146c66448f9b0efbdd16b999b07"
  -X DELETE

```


> The above command returns JSON structured like this:

```json
{
    "id": "ce671146c66448f9b0efbdd16b999b07",
    "resource": "buyer",
    "deleted": true
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://localhost:3000/v1/buyers/:buyer_id`

### URL Parameters

Parameter | Description
--------- | -----------
buyer_id | The ID of the buyer to delete

# Cards

## Create a Card
### HTTP Request
`POST http://localhost:3000/v1/cards`

This endpoint creates a card.

```shell
curl -X POST -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/cards" \
  -d '{"holder_name":"João Testador",
    "expiration_month":"10",
    "expiration_year": "2019",
    "security_code": "518",
    "card_number": "5316182431291479"}'
```

Parameter        | Description                              | Required? | Observation
---------        | -----------------------------------------| --------- | -----
holder_name      | string - holder_name of the card         | yes       |
expiration_month | string - expiration_month of the card    | yes       |
expiration_year  | string - expiration_year of the card     | yes       |
security_code    | string - security_code of the card       | yes       |
card_number      | string - card_number of the card         | yes       |


> The above command returns JSON structured like this:

```json
{
    "id": "a2cfea555fcd4b16a04e2006b8ccd870",
    "resource": "token",
    "used": false,
    "type": "card",
    "card": {
        "id": "0062d96825424112913dbded354c01ea",
        "resource": "card",
        "description": null,
        "card_brand": "MasterCard",
        "first4_digits": "5316",
        "expiration_month": "10",
        "expiration_year": "2019",
        "holder_name": "João Testador",
        "is_active": false,
        "is_valid": true,
        "is_verified": false,
        "customer": null,
        "fingerprint": "7511b78e35c079de0dd21373f2aeac1c5f7344aefdb459ff7e340e32dc0f2411",
        "address": null,
        "verification_checklist": {
            "postal_code_check": "unchecked",
            "security_code_check": "unchecked",
            "address_line1_check": "unchecked"
        },
        "metadata": {},
        "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/cards/0062d96825424112913dbded354c01ea",
        "created_at": "2018-08-27T13:16:32+00:00",
        "updated_at": "2018-08-27T13:16:32+00:00"
    },
    "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/tokens/a2cfea555fcd4b16a04e2006b8ccd870",
    "created_at": "2018-08-27T13:16:32+00:00",
    "updated_at": "2018-08-27T13:16:32+00:00"
}
```

## Get all Cards

```shell
curl "http://localhost:3000/v1/cards"

```

> The above command returns JSON structured like this:

```json
{
    "resource": "list",
    "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/cards?limit=100&offset=0",
    "items": [
        {
            "id": "3cd5d236a31141db87ce7b90e66321f4",
            "resource": "card",
            "description": null,
            "card_brand": "MasterCard",
            "first4_digits": "5425",
            "expiration_month": "1",
            "expiration_year": "2019",
            "holder_name": "teste",
            "is_active": false,
            "is_valid": true,
            "is_verified": false,
            "customer": null,
            "fingerprint": "b7c2312154b6c4860a55b1031448e7d8bfdafd50b965552910df79b7e4267e3e",
            "address": null,
            "verification_checklist": {
                "postal_code_check": "unchecked",
                "security_code_check": "unchecked",
                "address_line1_check": "unchecked"
            },
            "metadata": {},
            "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/cards/3cd5d236a31141db87ce7b90e66321f4",
            "created_at": "2018-08-23T13:31:41+00:00",
            "updated_at": "2018-08-23T13:31:41+00:00"
        },
        {
            "id": "9d29d52a789d4fed81fca0c7d91f327b",
            "resource": "card",
            "description": null,
            "card_brand": "MasterCard",
            "first4_digits": "5425",
            "expiration_month": "1",
            "expiration_year": "2019",
            "holder_name": "teste",
            "is_active": false,
            "is_valid": true,
            "is_verified": false,
            "customer": null,
            "fingerprint": "b7c2312154b6c4860a55b1031448e7d8bfdafd50b965552910df79b7e4267e3e",
            "address": null,
            "verification_checklist": {
                "postal_code_check": "unchecked",
                "security_code_check": "unchecked",
                "address_line1_check": "unchecked"
            },
            "metadata": {},
            "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/cards/9d29d52a789d4fed81fca0c7d91f327b",
            "created_at": "2018-08-23T12:39:26+00:00",
            "updated_at": "2018-08-23T12:39:26+00:00"
        }
    ],
    "limit": 100,
    "offset": 0,
    "has_more": false,
    "query_count": 2,
    "total": 2
}
```

This endpoint retrieves all cards.

### HTTP Request

`GET http://localhost:3000/v1/cards`



## Get a specific Card


```shell
curl "http://localhost:3000/v1/cards/3cd5d236a31141db87ce7b90e66321f4"

```
> The above command returns JSON structured like this:

```json
{
    "id": "3cd5d236a31141db87ce7b90e66321f4",
    "resource": "card",
    "description": null,
    "card_brand": "MasterCard",
    "first4_digits": "5425",
    "expiration_month": "1",
    "expiration_year": "2019",
    "holder_name": "teste",
    "is_active": false,
    "is_valid": true,
    "is_verified": false,
    "customer": null,
    "fingerprint": "b7c2312154b6c4860a55b1031448e7d8bfdafd50b965552910df79b7e4267e3e",
    "address": null,
    "verification_checklist": {
        "postal_code_check": "unchecked",
        "security_code_check": "unchecked",
        "address_line1_check": "unchecked"
    },
    "metadata": {},
    "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/cards/3cd5d236a31141db87ce7b90e66321f4",
    "created_at": "2018-08-23T13:31:41+00:00",
    "updated_at": "2018-08-23T13:31:41+00:00"
}
```

This endpoint retrieves a specific buyer.


### HTTP Request

`GET http://localhost:3000/v1/cards/:card_id`

### URL Parameters

Parameter | Description
--------- | -----------
card_id | The ID of the card to retrieve

## Delete a specific Card


```shell
curl "http://localhost:3000/v1/cards/3cd5d236a31141db87ce7b90e66321f4" \
  -X DELETE

```


> The above command returns JSON structured like this:

```json
{
    "id": "3cd5d236a31141db87ce7b90e66321f4",
    "resource": "card",
    "deleted": true
}
```

This endpoint deletes a specific card.

### HTTP Request

`DELETE http://localhost:3000/v1/cards/:card_id`

### URL Parameters

Parameter | Description
--------- | -----------
card_id  | The ID of the card to delete

## Associate a card to a buyer


```shell
curl -X POST -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/cards/associate_card_buyer" \
  -d '{"token": "a2cfea555fcd4b16a04e2006b8ccd870",
	   "customer": "64428de9655a4694bb3ff5e81d5af546"}'
```


> The above command returns JSON structured like this:

```json
{
    "id": "0062d96825424112913dbded354c01ea",
    "resource": "card",
    "description": null,
    "card_brand": "MasterCard",
    "first4_digits": "5316",
    "expiration_month": "10",
    "expiration_year": "2019",
    "holder_name": "João Testador",
    "is_active": true,
    "is_valid": true,
    "is_verified": false,
    "customer": "64428de9655a4694bb3ff5e81d5af546",
    "fingerprint": "7511b78e35c079de0dd21373f2aeac1c5f7344aefdb459ff7e340e32dc0f2411",
    "address": null,
    "verification_checklist": {
        "postal_code_check": "unchecked",
        "security_code_check": "fail",
        "address_line1_check": "unchecked"
    },
    "metadata": {},
    "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/cards/0062d96825424112913dbded354c01ea",
    "created_at": "2018-08-27T13:16:32+00:00",
    "updated_at": "2018-08-27T13:46:25+00:00"
}
```

This endpoint associate a card to a buyer.

### HTTP Request

`POST http://localhost:3000/v1/cards/associate_card_buyer`

### URL Parameters

Parameter | Description
--------- | -----------
token     | card token, returned when its created. can be used only one time.
customer  | buyer id

# Transactions

## Create a Transaction
### HTTP Request
`POST http://localhost:3000/v1/transaction`

This endpoint creates a transaction.

```shell
curl -X POST -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/transactions" \
  -d '{"amount":"10032",
       "customer":"64428de9655a4694bb3ff5e81d5af546",
       "payment_type": "credit",
        "number_installments": "5"
     }'
```

Parameter    | Description                              | Required? | Observation
---------    | -----------------------------------------| --------- | -----
amount       | integer - holder_name of the card         | yes       | in cents $
customer     | string - buyer id for recurrent charge   | no        | buyer id from bloom user
payment_type | string - expiration_year of the card     | no        | Default its credit
installment_plan.number_installments | integer - number of installments | yes | value range from (0 - 10)
token | string - card token for one unique payment     | no        |
on_behalf_of | string - seller id for payment     | no        | Default its Bloom Tester SellerId
capture | string     | no        |  capture transaction (true) or create pre-authorization (false) to capture later


> The above command returns JSON structured like this:

```json
{
    "id": "84824e3160a7431fb5004d41eaca4e76",
    "resource": "transaction",
    "status": "succeeded",
    "amount": "100.32",
    "original_amount": "100.32",
    "currency": "BRL",
    "description": null,
    "payment_type": "credit",
    "transaction_number": "Z133937-000260004",
    "gateway_authorizer": "cielo",
    "app_transaction_uid": null,
    "refunds": null,
    "rewards": null,
    "discounts": null,
    "pre_authorization": null,
    "sales_receipt": "12a752faa6dd40b3b04232631ca37610",
    "on_behalf_of": "cfa96058daa74d279d17f4908e7f6578",
    "customer": "64428de9655a4694bb3ff5e81d5af546",
    "statement_descriptor": "CANALBLOOM",
    "payment_method": {
        "id": "0062d96825424112913dbded354c01ea",
        "resource": "card",
        "description": null,
        "card_brand": "MasterCard",
        "first4_digits": "5316",
        "last4_digits": "1479",
        "expiration_month": "10",
        "expiration_year": "2019",
        "holder_name": "João Testador",
        "is_active": true,
        "is_valid": true,
        "is_verified": false,
        "customer": "64428de9655a4694bb3ff5e81d5af546",
        "fingerprint": "7511b78e35c079de0dd21373f2aeac1c5f7344aefdb459ff7e340e32dc0f2411",
        "address": null,
        "verification_checklist": {
            "postal_code_check": "unchecked",
            "security_code_check": "fail",
            "address_line1_check": "unchecked"
        },
        "metadata": {},
        "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/cards/0062d96825424112913dbded354c01ea",
        "created_at": "2018-08-27T13:16:32+00:00",
        "updated_at": "2018-08-27T13:46:25+00:00"
    },
    "point_of_sale": {
        "entry_mode": "manually_keyed",
        "identification_number": null
    },
    "installment_plan": {
        "number_installments": "5",
        "mode": "interest_free"
    },
    "refunded": false,
    "voided": false,
    "captured": true,
    "fees": "4.00",
    "fee_details": [
        {
            "amount": "4.00",
            "prepaid": false,
            "currency": "BRL",
            "type": "zoop_fee_brazil",
            "is_gateway_fee": false,
            "description": "Zoop card-present transaction fee"
        }
    ],
    "location_latitude": null,
    "location_longitude": null,
    "individual": null,
    "business": null,
    "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/transactions/84824e3160a7431fb5004d41eaca4e76",
    "metadata": {},
    "expected_on": "2018-09-26T00:00:00+00:00",
    "created_at": "2018-08-27T14:23:50+00:00",
    "updated_at": "2018-08-27T14:23:52+00:00",
    "payment_authorization": {
        "authorizer_id": "000260004",
        "authorization_code": "133937",
        "authorization_nsu": "20180510122911535"
    },
    "history": [
        {
            "id": "952f6f67a8784290a9643cfb6f68cd8d",
            "transaction": "84824e3160a7431fb5004d41eaca4e76",
            "amount": "100.32",
            "operation_type": "created",
            "status": "succeeded",
            "response_code": null,
            "response_message": null,
            "authorization_code": null,
            "authorizer_id": null,
            "authorization_nsu": null,
            "created_at": "2018-08-27 14:23:50"
        },
        {
            "id": "7c19a005b0cd417e81514b0d85d4a0eb",
            "transaction": "84824e3160a7431fb5004d41eaca4e76",
            "amount": "100.32",
            "operation_type": "authorization",
            "status": "succeeded",
            "response_code": "00",
            "response_message": null,
            "authorization_code": "133937",
            "authorizer_id": "000260004",
            "authorization_nsu": "20180510122911535",
            "created_at": "2018-08-27 14:23:52"
        }
    ]
}
```

## Get all Transactions

```shell
curl "http://localhost:3000/v1/transactions"

```

> The above command returns JSON structured like this:

```json
{
    "resource": "list",
    "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/transactions",
    "items": [
        {
            "id": "669a29234d6a4a83bd37542793282abc",
            "resource": "transaction",
            "status": "succeeded",
            "amount": "100.32",
            "original_amount": "100.32",
            "currency": "BRL",
            "description": null,
            "payment_type": "credit",
            "transaction_number": "Z133937-000260004",
            "gateway_authorizer": "cielo",
            "app_transaction_uid": null,
            "refunds": null,
            "rewards": null,
            "discounts": null,
            "pre_authorization": null,
            "sales_receipt": "055310be5b4244bf8da006a449368420",
            "on_behalf_of": "cfa96058daa74d279d17f4908e7f6578",
            "customer": "64428de9655a4694bb3ff5e81d5af546",
            "statement_descriptor": "CANALBLOOM",
            "payment_method": {
                "id": "0062d96825424112913dbded354c01ea",
                "resource": "card",
                "description": null,
                "card_brand": "MasterCard",
                "first4_digits": "5316",
                "last4_digits": "1479",
                "expiration_month": "10",
                "expiration_year": "2019",
                "holder_name": "João Testador",
                "is_active": true,
                "is_valid": true,
                "is_verified": false,
                "customer": "64428de9655a4694bb3ff5e81d5af546",
                "fingerprint": "7511b78e35c079de0dd21373f2aeac1c5f7344aefdb459ff7e340e32dc0f2411",
                "address": null,
                "verification_checklist": {
                    "postal_code_check": "unchecked",
                    "security_code_check": "fail",
                    "address_line1_check": "unchecked"
                },
                "metadata": {},
                "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/cards/0062d96825424112913dbded354c01ea",
                "created_at": "2018-08-27T13:16:32+00:00",
                "updated_at": "2018-08-27T13:46:25+00:00"
            },
            "point_of_sale": {
                "entry_mode": "manually_keyed",
                "identification_number": null
            },
            "installment_plan": {
                "number_installments": "5",
                "mode": "interest_free"
            },
            "refunded": false,
            "voided": false,
            "captured": true,
            "fees": "4.00",
            "fee_details": [
                {
                    "amount": "4.00",
                    "prepaid": false,
                    "currency": "BRL",
                    "type": "zoop_fee_brazil",
                    "is_gateway_fee": false,
                    "description": "Zoop card-present transaction fee"
                }
            ],
            "location_latitude": null,
            "location_longitude": null,
            "individual": null,
            "business": null,
            "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/transactions/669a29234d6a4a83bd37542793282abc",
            "metadata": {},
            "expected_on": "2018-09-26T00:00:00+00:00",
            "created_at": "2018-08-27T14:26:18+00:00",
            "updated_at": "2018-08-27T14:26:20+00:00",
            "payment_authorization": {
                "authorizer_id": "000260004",
                "authorization_code": "133937",
                "authorization_nsu": "20180510122911535"
            },
            "history": [
                {
                    "id": "3cb8c44457794f6c87adedba4f16cd32",
                    "transaction": "669a29234d6a4a83bd37542793282abc",
                    "amount": "100.32",
                    "operation_type": "created",
                    "status": "succeeded",
                    "response_code": null,
                    "response_message": null,
                    "authorization_code": null,
                    "authorizer_id": null,
                    "authorization_nsu": null,
                    "created_at": "2018-08-27 14:26:18"
                },
                {
                    "id": "81b2a682fce844998afa920a4b8705cd",
                    "transaction": "669a29234d6a4a83bd37542793282abc",
                    "amount": "100.32",
                    "operation_type": "authorization",
                    "status": "succeeded",
                    "response_code": "00",
                    "response_message": null,
                    "authorization_code": "133937",
                    "authorizer_id": "000260004",
                    "authorization_nsu": "20180510122911535",
                    "created_at": "2018-08-27 14:26:20"
                }
            ]
        },
        {
            "id": "6fcbc26bf8d84bd486eb02bb5951a1d7",
            "resource": "transaction",
            "status": "succeeded",
            "amount": "100.32",
            "original_amount": "100.32",
            "currency": "BRL",
            "description": null,
            "payment_type": "credit",
            "transaction_number": "Z133937-000260004",
            "gateway_authorizer": "cielo",
            "app_transaction_uid": null,
            "refunds": null,
            "rewards": null,
            "discounts": null,
            "pre_authorization": null,
            "sales_receipt": "01c955469a8c4d24809ba0357f43c049",
            "on_behalf_of": "cfa96058daa74d279d17f4908e7f6578",
            "customer": "64428de9655a4694bb3ff5e81d5af546",
            "statement_descriptor": "CANALBLOOM",
            "payment_method": {
                "id": "0062d96825424112913dbded354c01ea",
                "resource": "card",
                "description": null,
                "card_brand": "MasterCard",
                "first4_digits": "5316",
                "last4_digits": "1479",
                "expiration_month": "10",
                "expiration_year": "2019",
                "holder_name": "João Testador",
                "is_active": true,
                "is_valid": true,
                "is_verified": false,
                "customer": "64428de9655a4694bb3ff5e81d5af546",
                "fingerprint": "7511b78e35c079de0dd21373f2aeac1c5f7344aefdb459ff7e340e32dc0f2411",
                "address": null,
                "verification_checklist": {
                    "postal_code_check": "unchecked",
                    "security_code_check": "fail",
                    "address_line1_check": "unchecked"
                },
                "metadata": {},
                "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/cards/0062d96825424112913dbded354c01ea",
                "created_at": "2018-08-27T13:16:32+00:00",
                "updated_at": "2018-08-27T13:46:25+00:00"
            },
            "point_of_sale": {
                "entry_mode": "manually_keyed",
                "identification_number": null
            },
            "installment_plan": {
                "number_installments": "5",
                "mode": "interest_free"
            },
            "refunded": false,
            "voided": false,
            "captured": true,
            "fees": "4.00",
            "fee_details": [
                {
                    "amount": "4.00",
                    "prepaid": false,
                    "currency": "BRL",
                    "type": "zoop_fee_brazil",
                    "is_gateway_fee": false,
                    "description": "Zoop card-present transaction fee"
                }
            ],
            "location_latitude": null,
            "location_longitude": null,
            "individual": null,
            "business": null,
            "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/transactions/6fcbc26bf8d84bd486eb02bb5951a1d7",
            "metadata": {},
            "expected_on": "2018-09-26T00:00:00+00:00",
            "created_at": "2018-08-27T14:26:05+00:00",
            "updated_at": "2018-08-27T14:26:07+00:00",
            "payment_authorization": {
                "authorizer_id": "000260004",
                "authorization_code": "133937",
                "authorization_nsu": "20180510122911535"
            },
            "history": [
                {
                    "id": "1638f0d5805345cd81d5a57cdb2cfde0",
                    "transaction": "6fcbc26bf8d84bd486eb02bb5951a1d7",
                    "amount": "100.32",
                    "operation_type": "created",
                    "status": "succeeded",
                    "response_code": null,
                    "response_message": null,
                    "authorization_code": null,
                    "authorizer_id": null,
                    "authorization_nsu": null,
                    "created_at": "2018-08-27 14:26:05"
                },
                {
                    "id": "cccdf4d0dc3943c89d784b55e5f03252",
                    "transaction": "6fcbc26bf8d84bd486eb02bb5951a1d7",
                    "amount": "100.32",
                    "operation_type": "authorization",
                    "status": "succeeded",
                    "response_code": "00",
                    "response_message": null,
                    "authorization_code": "133937",
                    "authorizer_id": "000260004",
                    "authorization_nsu": "20180510122911535",
                    "created_at": "2018-08-27 14:26:07"
                }
            ]
        },
        {
            "id": "791277c3bf034ad38954bfa972860d48",
            "resource": "transaction",
            "status": "succeeded",
            "amount": "100.32",
            "original_amount": "100.32",
            "currency": "BRL",
            "description": null,
            "payment_type": "credit",
            "transaction_number": "Z133937-000260004",
            "gateway_authorizer": "cielo",
            "app_transaction_uid": null,
            "refunds": null,
            "rewards": null,
            "discounts": null,
            "pre_authorization": null,
            "sales_receipt": "28d5114b52954b23bd3d545d13293318",
            "on_behalf_of": "cfa96058daa74d279d17f4908e7f6578",
            "customer": "64428de9655a4694bb3ff5e81d5af546",
            "statement_descriptor": "CANALBLOOM",
            "payment_method": {
                "id": "0062d96825424112913dbded354c01ea",
                "resource": "card",
                "description": null,
                "card_brand": "MasterCard",
                "first4_digits": "5316",
                "last4_digits": "1479",
                "expiration_month": "10",
                "expiration_year": "2019",
                "holder_name": "João Testador",
                "is_active": true,
                "is_valid": true,
                "is_verified": false,
                "customer": "64428de9655a4694bb3ff5e81d5af546",
                "fingerprint": "7511b78e35c079de0dd21373f2aeac1c5f7344aefdb459ff7e340e32dc0f2411",
                "address": null,
                "verification_checklist": {
                    "postal_code_check": "unchecked",
                    "security_code_check": "fail",
                    "address_line1_check": "unchecked"
                },
                "metadata": {},
                "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/cards/0062d96825424112913dbded354c01ea",
                "created_at": "2018-08-27T13:16:32+00:00",
                "updated_at": "2018-08-27T13:46:25+00:00"
            },
            "point_of_sale": {
                "entry_mode": "manually_keyed",
                "identification_number": null
            },
            "installment_plan": {
                "number_installments": "5",
                "mode": "interest_free"
            },
            "refunded": false,
            "voided": false,
            "captured": true,
            "fees": "4.00",
            "fee_details": [
                {
                    "amount": "4.00",
                    "prepaid": false,
                    "currency": "BRL",
                    "type": "zoop_fee_brazil",
                    "is_gateway_fee": false,
                    "description": "Zoop card-present transaction fee"
                }
            ],
            "location_latitude": null,
            "location_longitude": null,
            "individual": null,
            "business": null,
            "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/transactions/791277c3bf034ad38954bfa972860d48",
            "metadata": {},
            "expected_on": "2018-09-26T00:00:00+00:00",
            "created_at": "2018-08-27T14:24:21+00:00",
            "updated_at": "2018-08-27T14:24:23+00:00",
            "payment_authorization": {
                "authorizer_id": "000260004",
                "authorization_code": "133937",
                "authorization_nsu": "20180510122911535"
            },
            "history": [
                {
                    "id": "96fa92ff0db7423ba6bbdd9ab04daa32",
                    "transaction": "791277c3bf034ad38954bfa972860d48",
                    "amount": "100.32",
                    "operation_type": "created",
                    "status": "succeeded",
                    "response_code": null,
                    "response_message": null,
                    "authorization_code": null,
                    "authorizer_id": null,
                    "authorization_nsu": null,
                    "created_at": "2018-08-27 14:24:21"
                },
                {
                    "id": "bbb898c4ad414555bb6e0bfa731b1e7d",
                    "transaction": "791277c3bf034ad38954bfa972860d48",
                    "amount": "100.32",
                    "operation_type": "authorization",
                    "status": "succeeded",
                    "response_code": "00",
                    "response_message": null,
                    "authorization_code": "133937",
                    "authorizer_id": "000260004",
                    "authorization_nsu": "20180510122911535",
                    "created_at": "2018-08-27 14:24:23"
                }
            ]
        },
        {
            "id": "84824e3160a7431fb5004d41eaca4e76",
            "resource": "transaction",
            "status": "succeeded",
            "amount": "100.32",
            "original_amount": "100.32",
            "currency": "BRL",
            "description": null,
            "payment_type": "credit",
            "transaction_number": "Z133937-000260004",
            "gateway_authorizer": "cielo",
            "app_transaction_uid": null,
            "refunds": null,
            "rewards": null,
            "discounts": null,
            "pre_authorization": null,
            "sales_receipt": "12a752faa6dd40b3b04232631ca37610",
            "on_behalf_of": "cfa96058daa74d279d17f4908e7f6578",
            "customer": "64428de9655a4694bb3ff5e81d5af546",
            "statement_descriptor": "CANALBLOOM",
            "payment_method": {
                "id": "0062d96825424112913dbded354c01ea",
                "resource": "card",
                "description": null,
                "card_brand": "MasterCard",
                "first4_digits": "5316",
                "last4_digits": "1479",
                "expiration_month": "10",
                "expiration_year": "2019",
                "holder_name": "João Testador",
                "is_active": true,
                "is_valid": true,
                "is_verified": false,
                "customer": "64428de9655a4694bb3ff5e81d5af546",
                "fingerprint": "7511b78e35c079de0dd21373f2aeac1c5f7344aefdb459ff7e340e32dc0f2411",
                "address": null,
                "verification_checklist": {
                    "postal_code_check": "unchecked",
                    "security_code_check": "fail",
                    "address_line1_check": "unchecked"
                },
                "metadata": {},
                "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/cards/0062d96825424112913dbded354c01ea",
                "created_at": "2018-08-27T13:16:32+00:00",
                "updated_at": "2018-08-27T13:46:25+00:00"
            },
            "point_of_sale": {
                "entry_mode": "manually_keyed",
                "identification_number": null
            },
            "installment_plan": {
                "number_installments": "5",
                "mode": "interest_free"
            },
            "refunded": false,
            "voided": false,
            "captured": true,
            "fees": "4.00",
            "fee_details": [
                {
                    "amount": "4.00",
                    "prepaid": false,
                    "currency": "BRL",
                    "type": "zoop_fee_brazil",
                    "is_gateway_fee": false,
                    "description": "Zoop card-present transaction fee"
                }
            ],
            "location_latitude": null,
            "location_longitude": null,
            "individual": null,
            "business": null,
            "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/transactions/84824e3160a7431fb5004d41eaca4e76",
            "metadata": {},
            "expected_on": "2018-09-26T00:00:00+00:00",
            "created_at": "2018-08-27T14:23:50+00:00",
            "updated_at": "2018-08-27T14:23:52+00:00",
            "payment_authorization": {
                "authorizer_id": "000260004",
                "authorization_code": "133937",
                "authorization_nsu": "20180510122911535"
            },
            "history": [
                {
                    "id": "952f6f67a8784290a9643cfb6f68cd8d",
                    "transaction": "84824e3160a7431fb5004d41eaca4e76",
                    "amount": "100.32",
                    "operation_type": "created",
                    "status": "succeeded",
                    "response_code": null,
                    "response_message": null,
                    "authorization_code": null,
                    "authorizer_id": null,
                    "authorization_nsu": null,
                    "created_at": "2018-08-27 14:23:50"
                },
                {
                    "id": "7c19a005b0cd417e81514b0d85d4a0eb",
                    "transaction": "84824e3160a7431fb5004d41eaca4e76",
                    "amount": "100.32",
                    "operation_type": "authorization",
                    "status": "succeeded",
                    "response_code": "00",
                    "response_message": null,
                    "authorization_code": "133937",
                    "authorizer_id": "000260004",
                    "authorization_nsu": "20180510122911535",
                    "created_at": "2018-08-27 14:23:52"
                }
            ]
        }
    ],
    "has_more": false,
    "limit": 100,
    "total_pages": 1,
    "page": 1,
    "offset": 0,
    "total": "4",
    "query_count": "4"
}
```

This endpoint retrieves all transactions.

### HTTP Request

`GET http://localhost:3000/v1/transactions`



## Get a specific Transaction


```shell
curl "http://localhost:3000/v1/transactions/84824e3160a7431fb5004d41eaca4e76"

```
> The above command returns JSON structured like this:

```json
{
    "id": "84824e3160a7431fb5004d41eaca4e76",
    "resource": "transaction",
    "status": "succeeded",
    "amount": "100.32",
    "original_amount": "100.32",
    "currency": "BRL",
    "description": null,
    "payment_type": "credit",
    "transaction_number": "Z133937-000260004",
    "gateway_authorizer": "cielo",
    "app_transaction_uid": null,
    "refunds": null,
    "rewards": null,
    "discounts": null,
    "pre_authorization": null,
    "sales_receipt": "12a752faa6dd40b3b04232631ca37610",
    "on_behalf_of": "cfa96058daa74d279d17f4908e7f6578",
    "customer": "64428de9655a4694bb3ff5e81d5af546",
    "statement_descriptor": "CANALBLOOM",
    "payment_method": {
        "id": "0062d96825424112913dbded354c01ea",
        "resource": "card",
        "description": null,
        "card_brand": "MasterCard",
        "first4_digits": "5316",
        "last4_digits": "1479",
        "expiration_month": "10",
        "expiration_year": "2019",
        "holder_name": "João Testador",
        "is_active": true,
        "is_valid": true,
        "is_verified": false,
        "customer": "64428de9655a4694bb3ff5e81d5af546",
        "fingerprint": "7511b78e35c079de0dd21373f2aeac1c5f7344aefdb459ff7e340e32dc0f2411",
        "address": null,
        "verification_checklist": {
            "postal_code_check": "unchecked",
            "security_code_check": "fail",
            "address_line1_check": "unchecked"
        },
        "metadata": {},
        "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/cards/0062d96825424112913dbded354c01ea",
        "created_at": "2018-08-27T13:16:32+00:00",
        "updated_at": "2018-08-27T13:46:25+00:00"
    },
    "point_of_sale": {
        "entry_mode": "manually_keyed",
        "identification_number": null
    },
    "installment_plan": {
        "number_installments": "5",
        "mode": "interest_free"
    },
    "refunded": false,
    "voided": false,
    "captured": true,
    "fees": "4.00",
    "fee_details": [
        {
            "amount": "4.00",
            "prepaid": false,
            "currency": "BRL",
            "type": "zoop_fee_brazil",
            "is_gateway_fee": false,
            "description": "Zoop card-present transaction fee"
        }
    ],
    "location_latitude": null,
    "location_longitude": null,
    "individual": null,
    "business": null,
    "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/transactions/84824e3160a7431fb5004d41eaca4e76",
    "metadata": {},
    "expected_on": "2018-09-26T00:00:00+00:00",
    "created_at": "2018-08-27T14:23:50+00:00",
    "updated_at": "2018-08-27T14:23:52+00:00",
    "payment_authorization": {
        "authorizer_id": "000260004",
        "authorization_code": "133937",
        "authorization_nsu": "20180510122911535"
    },
    "history": [
        {
            "id": "952f6f67a8784290a9643cfb6f68cd8d",
            "transaction": "84824e3160a7431fb5004d41eaca4e76",
            "amount": "100.32",
            "operation_type": "created",
            "status": "succeeded",
            "response_code": null,
            "response_message": null,
            "authorization_code": null,
            "authorizer_id": null,
            "authorization_nsu": null,
            "created_at": "2018-08-27 14:23:50"
        },
        {
            "id": "7c19a005b0cd417e81514b0d85d4a0eb",
            "transaction": "84824e3160a7431fb5004d41eaca4e76",
            "amount": "100.32",
            "operation_type": "authorization",
            "status": "succeeded",
            "response_code": "00",
            "response_message": null,
            "authorization_code": "133937",
            "authorizer_id": "000260004",
            "authorization_nsu": "20180510122911535",
            "created_at": "2018-08-27 14:23:52"
        }
    ]
}
```

This endpoint retrieves a specific transaction.


### HTTP Request

`GET http://localhost:3000/v1/transactions/:transaction_id`

### URL Parameters

Parameter    | Description                              | Required? | Observation
---------    | -----------------------------------------| --------- | -----
transaction_id | The ID of the transaction to retrieve | yes       |
on_behalf_of | string - seller id for payment     | no        | Default its Bloom Tester SellerId

## Reverse a specific Transaction


```shell
curl -X POST -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/transactions/84824e3160a7431fb5004d41eaca4e76/reverse" \
  -d '{"amount":"10032"}'
```

> The above command returns JSON structured like this:

```json
{
    "id": "84824e3160a7431fb5004d41eaca4e76",
    "resource": "transaction",
    "status": "canceled",
    "amount": "100.32",
    "original_amount": "100.32",
    "currency": "BRL",
    "description": null,
    "payment_type": "credit",
    "transaction_number": "Z133937-000260004",
    "gateway_authorizer": "cielo",
    "app_transaction_uid": null,
    "refunds": null,
    "rewards": null,
    "discounts": null,
    "pre_authorization": null,
    "sales_receipt": "12a752faa6dd40b3b04232631ca37610",
    "on_behalf_of": "cfa96058daa74d279d17f4908e7f6578",
    "customer": "64428de9655a4694bb3ff5e81d5af546",
    "statement_descriptor": "CANALBLOOM",
    "payment_method": {
        "id": "0062d96825424112913dbded354c01ea",
        "resource": "card",
        "description": null,
        "card_brand": "MasterCard",
        "first4_digits": "5316",
        "expiration_month": "10",
        "expiration_year": "2019",
        "holder_name": "João Testador",
        "is_active": true,
        "is_valid": true,
        "is_verified": false,
        "customer": "64428de9655a4694bb3ff5e81d5af546",
        "fingerprint": "7511b78e35c079de0dd21373f2aeac1c5f7344aefdb459ff7e340e32dc0f2411",
        "address": null,
        "verification_checklist": {
            "postal_code_check": "unchecked",
            "security_code_check": "fail",
            "address_line1_check": "unchecked"
        },
        "metadata": {},
        "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/cards/0062d96825424112913dbded354c01ea",
        "created_at": "2018-08-27T13:16:32+00:00",
        "updated_at": "2018-08-27T13:46:25+00:00"
    },
    "source": null,
    "point_of_sale": {
        "entry_mode": "manually_keyed",
        "identification_number": null
    },
    "installment_plan": {
        "number_installments": "5",
        "mode": "interest_free"
    },
    "refunded": false,
    "voided": true,
    "captured": true,
    "fees": "0.00",
    "fee_details": null,
    "location_latitude": null,
    "location_longitude": null,
    "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/transactions/84824e3160a7431fb5004d41eaca4e76",
    "metadata": {},
    "expected_on": "2018-09-26T00:00:00+00:00",
    "created_at": "2018-08-27T14:23:50+00:00",
    "voided_at": "2018-08-27T14:35:43+00:00",
    "payment_authorization": {
        "authorizer_id": "000260004",
        "authorization_code": "133937",
        "authorization_nsu": "20180510122911535"
    },
    "history": [
        {
            "id": "952f6f67a8784290a9643cfb6f68cd8d",
            "transaction": "84824e3160a7431fb5004d41eaca4e76",
            "amount": "100.32",
            "operation_type": "created",
            "status": "succeeded",
            "response_code": null,
            "response_message": null,
            "authorization_code": null,
            "authorizer_id": null,
            "authorization_nsu": null,
            "created_at": "2018-08-27 14:23:50"
        },
        {
            "id": "7c19a005b0cd417e81514b0d85d4a0eb",
            "transaction": "84824e3160a7431fb5004d41eaca4e76",
            "amount": "100.32",
            "operation_type": "authorization",
            "status": "succeeded",
            "response_code": "00",
            "response_message": null,
            "authorization_code": "133937",
            "authorizer_id": "000260004",
            "authorization_nsu": "20180510122911535",
            "created_at": "2018-08-27 14:23:52"
        },
        {
            "id": "b11e952d900d4eae9c6ad1fe4d4a8a8c",
            "transaction": "84824e3160a7431fb5004d41eaca4e76",
            "amount": "100.32",
            "operation_type": "void",
            "status": "succeeded",
            "response_code": "0",
            "response_message": null,
            "authorization_code": "105016",
            "authorizer_id": "0126105452552",
            "authorization_nsu": "20180510122911537",
            "created_at": "2018-08-27 14:35:43"
        }
    ]
}

```

This endpoint deletes a specific card.


### HTTP Request

`POST http://localhost:3000/v1/transactions/:transaction_id/reverse`

### URL Parameters

Parameter    | Description                              | Required? | Observation
---------    | -----------------------------------------| --------- | -----
transaction_id | The ID of the transaction to retrieve | yes       |
on_behalf_of | string - seller id for payment     | no        | Default its Bloom Tester SellerId

## Capture a specific Transaction


```shell
curl -X POST -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/transactions/84824e3160a7431fb5004d41eaca4e76/capture" \
  -d '{"amount":"10032"}'
```

> The above command returns JSON structured like this:

```json
{
    "id": "669a29234d6a4a83bd37542793282abc",
    "resource": "transaction",
    "status": "succeeded",
    "amount": "100.32",
    "original_amount": "100.32",
    "currency": "BRL",
    "description": null,
    "payment_type": "credit",
    "transaction_number": "Z133937-000260004",
    "gateway_authorizer": "cielo",
    "app_transaction_uid": null,
    "refunds": null,
    "rewards": null,
    "discounts": null,
    "pre_authorization": null,
    "sales_receipt": "055310be5b4244bf8da006a449368420",
    "on_behalf_of": "cfa96058daa74d279d17f4908e7f6578",
    "customer": "64428de9655a4694bb3ff5e81d5af546",
    "statement_descriptor": "CANALBLOOM",
    "payment_method": {
        "id": "0062d96825424112913dbded354c01ea",
        "resource": "card",
        "description": null,
        "card_brand": "MasterCard",
        "first4_digits": "5316",
        "expiration_month": "10",
        "expiration_year": "2019",
        "holder_name": "João Testador",
        "is_active": true,
        "is_valid": true,
        "is_verified": false,
        "customer": "64428de9655a4694bb3ff5e81d5af546",
        "fingerprint": "7511b78e35c079de0dd21373f2aeac1c5f7344aefdb459ff7e340e32dc0f2411",
        "address": null,
        "verification_checklist": {
            "postal_code_check": "unchecked",
            "security_code_check": "fail",
            "address_line1_check": "unchecked"
        },
        "metadata": {},
        "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/cards/0062d96825424112913dbded354c01ea",
        "created_at": "2018-08-27T13:16:32+00:00",
        "updated_at": "2018-08-27T13:46:25+00:00"
    },
    "source": null,
    "point_of_sale": {
        "entry_mode": "manually_keyed",
        "identification_number": null
    },
    "installment_plan": {
        "number_installments": "5",
        "mode": "interest_free"
    },
    "refunded": false,
    "voided": false,
    "captured": true,
    "fees": "4.00",
    "fee_details": [
        {
            "amount": "4.00",
            "prepaid": false,
            "currency": "BRL",
            "type": "zoop_fee_brazil",
            "is_gateway_fee": false,
            "description": "Zoop card-present transaction fee"
        }
    ],
    "location_latitude": null,
    "location_longitude": null,
    "uri": "/v1/marketplaces/dasdnaojudh3quiwhdquiwdhquiwhd7892y3hd8/transactions/669a29234d6a4a83bd37542793282abc",
    "metadata": {},
    "expected_on": "2018-09-26T00:00:00+00:00",
    "created_at": "2018-08-27T14:26:18+00:00",
    "updated_at": "2018-08-27T14:26:20+00:00",
    "payment_authorization": {
        "authorizer_id": "000260004",
        "authorization_code": "133937",
        "authorization_nsu": "20180510122911535"
    },
    "history": [
        {
            "id": "3cb8c44457794f6c87adedba4f16cd32",
            "transaction": "669a29234d6a4a83bd37542793282abc",
            "amount": "100.32",
            "operation_type": "created",
            "status": "succeeded",
            "response_code": null,
            "response_message": null,
            "authorization_code": null,
            "authorizer_id": null,
            "authorization_nsu": null,
            "created_at": "2018-08-27 14:26:18"
        },
        {
            "id": "81b2a682fce844998afa920a4b8705cd",
            "transaction": "669a29234d6a4a83bd37542793282abc",
            "amount": "100.32",
            "operation_type": "authorization",
            "status": "succeeded",
            "response_code": "00",
            "response_message": null,
            "authorization_code": "133937",
            "authorizer_id": "000260004",
            "authorization_nsu": "20180510122911535",
            "created_at": "2018-08-27 14:26:20"
        }
    ]
}
```

This endpoint deletes a specific card.


### HTTP Request

`POST http://localhost:3000/v1/transactions/:transaction_id/capture`

### URL Parameters


Parameter    | Description                              | Required? | Observation
---------    | -----------------------------------------| --------- | -----
transaction_id | The ID of the transaction to retrieve | yes       |
on_behalf_of | string - seller id for payment     | no        | Default its Bloom Tester SellerId

# Vouchers

## Create a Voucher
### HTTP Request
`POST http://localhost:3000/v1/vouchers`

This endpoint creates a voucher.

```shell
curl -X POST -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/vouchers" \
  -d '{"expiration" :"10/10/2019","duration_days": 180,"company": "any"}'
```
Parameter | Description                              | Required? | Observation
--------- | -----------------------------------------| --------- | -----
company | string - name of the company               | no        |
duration_days | string - duration_days of the voucher| no        | default its 30 days
expiration | string - expiration of the voucher      | no        | format dd-mm-YYYY, default its 90 days after creation


> The above command returns JSON structured like this:

```json
{
    "id": 31,
    "display_id": "NYRK8E",
    "expiration": "2019-10-10T00:00:00.000Z",
    "company": "any",
    "user_email": null,
    "created_at": "2018-08-27T15:13:06.000Z",
    "updated_at": "2018-08-27T15:13:06.000Z",
    "duration_days": 77,
    "reclaimed_date": null,
    "reclaimed": false
}
```

## Update a Voucher
### HTTP Request
`PUT http://localhost:3000/v1/vouchers/:display_id`

This endpoint updates a voucher.

```shell
curl -X PUT -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/vouchers/NYRK8E" \
  -d '{"email":"teste@teste.com"}'
```
Parameter | Description                              | Required? | Observation
--------- | -----------------------------------------| --------- | -----
user_email | string - email of a bloom user          | yes       | must be a registered bloom user
duration_days | string - duration_days of the voucher| no        | default its 30 days
expiration | string - expiration of the voucher      | no        | format YYYY-mm-dd, default its 90 days after creation
company    | string - name of the company            | no        | nil its default
reclaimed  | boolean - if vouchers was used          | no        | defaults its true
reclaimed_date  | string - reclaimed date            | no        | defaults its DateTime.now
> The above command returns JSON structured like this:

```json
{
    "id": 31,
    "duration_days": 30,
    "expiration": "2018-11-25T15:22:53.000Z",
    "company": null,
    "reclaimed": true,
    "reclaimed_date": "2018-08-27T15:22:53.000Z",
    "user_email": "teste@teste.com",
    "display_id": "NYRK8E",
    "created_at": "2018-08-27T15:13:06.000Z",
    "updated_at": "2018-08-27T15:22:53.000Z"
}
```

## Get all Vouchers

```shell
curl "http://localhost:3000/v1/vouchers"

```

> The above command returns JSON structured like this:

```json
[
   {
      "id":2,
      "display_id":"67JN20",
      "expiration":"2018-11-22T15:58:05.000Z",
      "company":null,
      "user_email":"teste@teste.com",
      "created_at":"2018-08-24T14:54:51.000Z",
      "updated_at":"2018-08-24T15:58:06.000Z",
      "duration_days":30,
      "reclaimed_date":"2018-08-24T15:58:06.000Z",
      "reclaimed":true
   },
   {
      "id":3,
      "display_id":"PPTJM5",
      "expiration":null,
      "company":null,
      "user_email":null,
      "created_at":"2018-08-24T14:54:52.000Z",
      "updated_at":"2018-08-24T14:54:52.000Z",
      "duration_days":null,
      "reclaimed_date":null,
      "reclaimed":null
   }
]
```

This endpoint retrieves all vouchers.

### HTTP Request

`GET http://localhost:3000/v1/vouchers`



## Get a Specific Voucher


```shell
curl "http://localhost:3000/v1/vouchers/67JN20"

```

> The above command returns JSON structured like this:

```json
{
   "id":2,
   "display_id":"67JN20",
   "expiration":"2018-11-22T15:58:05.000Z",
   "company":null,
   "user_email":"teste@teste.com",
   "created_at":"2018-08-24T14:54:51.000Z",
   "updated_at":"2018-08-24T15:58:06.000Z",
   "duration_days":30,
   "reclaimed_date":"2018-08-24T15:58:06.000Z",
   "reclaimed":true
}
```

This endpoint retrieves a specific voucher.


### HTTP Request

`GET http://localhost:3000/v1/voucher/:display_id`

### URL Parameters

Parameter | Description
--------- | -----------
display_id | The ID of the voucher to retrieve

## Delete a Specific Voucher


```shell
curl "http://localhost:3000/v1/vouchers/67JN20" \
  -X DELETE
```


> The above command returns JSON structured like this:

```json
{
  "success":true,
  "msg":"voucher was removed"
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://localhost:3000/v1/vouchers/:display_id`

### URL Parameters

Parameter | Description
--------- | -----------
buyer_id | The ID of the buyer to delete
