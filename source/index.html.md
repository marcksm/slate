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
  -d '{"email":"email@email.com", "notes":"Anotações Gerais", "name": "Nome do Cliente"}'
```
Parameter    | Description                              | Required? | Observation
---------    | -----------------------------------------| --------- | -----
email        | string - email of the buyer              | yes       | email must be a registered bloom user
cpf_cnpj     | string - cpf of the buyer                | no        | CPF/CNPJ must be unique
name         | string - name of the buyer               | yes       |
notes        | string - notes                           | no        |
phone        | int32 - phone number - 9 digits          | no        |
phone_prefix | int32 - phone profix - 3 digits          | only if phone is sent |
zip_code     | string - cep                             | no         |
number       | int32 - number of address                | only if zip_code is sent |
street       | string - street address                  | only if zip_code is sent |
city         | string - city                            | no |
state        | string - state                           | no |
district     | string - district                        | only if zip_code is sent |
complement   | string - complement                      | no |


> The above command returns JSON structured like this:

```json
{
    "id": "77C2565F6F064A26ABED4255894224F0",
    "email": "email@email.com",
    "name": "Nome do Cliente",
    "notes": "Anotações Gerais",
    "created_at": "2013-11-18T14:58:30-02:00",
    "updated_at": "2013-11-18T14:58:30-02:00",
    "custom_variables":[]
}
```

## Update a Buyers
### HTTP Request
`PUT http://localhost:3000/v1/buyers/:buyer_id`

This endpoint creates a buyer.

```shell
curl -X PUT -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/buyers/64428de9655a4694bb3ff5e81d5af546" \
  -d '{"notes": "Novas Anotações Gerais", "name": "Novo Nome do Cliente"}'
```
Parameter    | Description                              | Required? | Observation
---------    | -----------------------------------------| --------- | -----
email        | string - email of the buyer              | yes       | email must be a registered bloom user
cpf_cnpj     | string - cpf of the buyer                | no        | CPF/CNPJ must be unique
name         | string - name of the buyer               | yes       |
notes        | string - notes                           | no        |
phone        | int32 - phone number - 9 digits          | no        |
phone_prefix | int32 - phone profix - 3 digits          | only if phone is sent |
zip_code     | string - cep                             | no         |
number       | int32 - number of address                | only if zip_code is sent |
street       | string - street address                  | only if zip_code is sent |
city         | string - city                            | no |
state        | string - state                           | no |
district     | string - district                        | only if zip_code is sent |
complement   | string - complement                      | no |

> The above command returns JSON structured like this:

```json
  {
    "id": "77C2565F6F064A26ABED4255894224F0",
    "email": "email@email.com",
    "name": "Novo Nome do Cliente",
    "notes": "Novas Anotações Gerais",
    "created_at": "2013-11-18T14:58:30-02:00",
    "updated_at": "2013-11-18T14:58:30-02:00",
    "custom_variables":[]
  }
```

## Get All Buyers

```shell
curl "http://localhost:3000/v1/buyers"

```

> The above command returns JSON structured like this:

```json
{
    "totalItems": 5,
    "items": [
        {
            "id": "FF3149CE52CB4A789925F154B489BFDD",
            "email": "email@email.com",
            "name": "Nome do Cliente",
            "notes": "Anotações Gerais",
            "created_at": "2013-11-18T14:58:30-02:00",
            "updated_at": "2013-11-18T14:58:30-02:00"
        },
        {
            "id": "912FD57927FA43DEB0223C819E18DDFE",
            "email": "email@email.com",
            "name": "Nome do Cliente",
            "notes": "Anotações Gerais",
            "created_at": "2013-11-18T14:58:30-02:00",
            "updated_at": "2013-11-18T14:58:30-02:00"
        },
        {
            "id": "32CE45D8B42B4AEEA3D1A1D9227E1790",
            "email": "email@gmail.com",
            "name": null,
            "notes": null,
            "created_at": "2013-11-18T14:58:30-02:00",
            "updated_at": "2013-11-18T14:58:30-02:00"
        },
        {
            "id": "1AF1B6EC280149708773FED03EB407AA",
            "email": "teste@gmail.com",
            "name": null,
            "notes": null,
            "created_at": "2013-11-18T14:58:30-02:00",
            "updated_at": "2013-11-18T14:58:30-02:00"
        },
        {
            "id": "D65B556E19ED4173976421E84EE7B251",
            "email": "cliente@gmail.com",
            "name": null,
            "notes": null,
            "created_at": "2013-11-18T14:58:30-02:00",
            "updated_at": "2013-11-18T14:58:30-02:00"
        }
    ]
}

```

This endpoint retrieves all buyers.

### HTTP Request

`GET http://localhost:3000/v1/buyers`



## Get a Specific Buyer


```shell
curl "http://localhost:3000/v1/buyers/77C2565F6F064A26ABED4255894224F0"

```


> The above command returns JSON structured like this:

```json
{
    "id": "77C2565F6F064A26ABED4255894224F0",
    "email": "email@email.com",
    "name": "Nome do Cliente",
    "notes": "Anotações Gerais",
    "created_at": "2013-11-18T14:58:30-02:00",
    "updated_at": "2013-11-18T14:58:30-02:00",
    "custom_variables":[]
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
curl "http://localhost:3000/v1/buyers/77C2565F6F064A26ABED4255894224F0"
  -X DELETE

```


> The above command returns JSON structured like this:

```json
{
    "id": "77C2565F6F064A26ABED4255894224F0",
    "email": "email@email.com",
    "name": "Novo Nome do Cliente",
    "notes": "Novas Anotações Gerais",
    "created_at": "2013-11-18T14:58:30-02:00",
    "updated_at": "2013-11-18T14:58:30-02:00",
    "custom_variables":[]
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
  -d '{
    "customer_id":"281E91739C1444FE92E26FEE196CF033",
    "number":"4111111111111111",
    "verification_value":"552",
    "first_name": "Joao",
    "last_name": "Silva",
    "month": "11",
    "year": "2019",
    "description": "Meu Cartão de Crédito"
  }'
```



Parameter          | Description                              | Required? | Observation
---------          | -----------------------------------------| --------- | -----
customer_id        | string - id of the client                | yes       |
number             | string - number of the card              | yes       |
verification_value | string - verification_value of the card  | yes       |
first_name         | string - first_name of the card          | yes       |
last_name          | string - last_name of the card           | yes       |
month              | string - month of the card               | yes       |
year               | string - year of the card                | yes       |
description        | string - description of the card         | yes       |


> The above command returns JSON structured like this:

```json
{
    "id": "9B41FB19CBA44913B1EF990A10382E7E",
    "description": "Meu Cartão de Crédito",
    "item_type": "credit_card",
    "data": {
        "holder_name": "Joao Silva",
        "display_number": "XXXX-XXXX-XXXX-1111",
        "brand": "visa",
        "month":12,
        "year":2022
    }
}
```

## Get all Cards from a client

```shell
curl "http://localhost:3000/v1/cards?id=7894OHDASDASD0A9432"

```

> The above command returns JSON structured like this:

```json
[{
    "id": "48D603C05F634244A1D3FC2BFF35D10A",
    "description": "Meu Cartão de Crédito Um",
    "item_type": "credit_card",
    "data": {
        "holder_name": "Joao Silva",
        "display_number": "XXXX-XXXX-XXXX-1111",
        "brand": "visa",
        "month":10,
        "year":2022
    }
}, {
    "id": "9B41FB19CBA44913B1EF990A10382E7E",
    "description": "Meu Cartão de Crédito Dois",
    "item_type": "credit_card",
    "data": {
        "holder_name": "Jose Santos",
        "display_number": "XXXX-XXXX-XXXX-1111",
        "brand": "visa",
        "month":7,
        "year":2019
    }
}]
```

This endpoint retrieves all cards.

### HTTP Request

`GET http://localhost:3000/v1/cards?id=:client_id`



## Get a specific card from a client


```shell
curl "http://localhost:3000/v1/cards/281E91739C1444FE92E26FEE196CF033?card_id=7AE0E8EC153B4D24B1984FCBF6A93704"

```
> The above command returns JSON structured like this:

```json
{
    "id": "7AE0E8EC153B4D24B1984FCBF6A93704",
    "description": "Meu Cartão de Crédito",
    "item_type": "credit_card",
    "customer_id": "281E91739C1444FE92E26FEE196CF033",
    "data": {
        "brand": "VISA",
        "holder_name": "Joao Silva",
        "display_number": "XXXX-XXXX-XXXX-1111",
        "bin": "411111",
        "month": 11,
        "year": 2019
    }
}
```

This endpoint retrieves a specific buyer.


### HTTP Request

`GET http://localhost:3000/v1/cards/:customer_id?id=:card_id`

### URL Parameters

Parameter | Description
--------- | -----------
card_id | The ID of the card to retrieve

## Delete a specific card from a client


```shell
curl "http://localhost:3000/v1/cards/281E91739C1444FE92E26FEE196CF033?card_id=7AE0E8EC153B4D24B1984FCBF6A93704" \
  -X DELETE

```


> The above command returns JSON structured like this:

```json
{
    "id": "7AE0E8EC153B4D24B1984FCBF6A93704",
    "description": "Meu Cartão de Crédito",
    "item_type": "credit_card",
    "customer_id": "281E91739C1444FE92E26FEE196CF033",
    "data": {
        "brand": "VISA",
        "holder_name": "Joao Silva",
        "display_number": "XXXX-XXXX-XXXX-1111",
        "bin": "411111",
        "month": 11,
        "year": 2019
    }
}
```

This endpoint deletes a specific card.

### HTTP Request

`DELETE http://localhost:3000/v1/cards/:customer_id?id=:card_id`

### URL Parameters

Parameter | Description
--------- | -----------
card_id  | The ID of the card to delete

# Plans (USE IUGU DASHBOARD)
## Create a Plan  (USE IUGU DASHBOARD)
### HTTP Request
`POST http://localhost:3000/v1/plans`

This endpoint creates a plan.

```shell
curl -X POST -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/plans" \
  -d '{"name" :"Plano Básico",
      "identifier": "basic_plan",
      "interval": 1,
      "interval_type": "months",
      "value_cents": 1000
    }'
```


Parameter | Description                              | Required? | Observation
--------- | -----------------------------------------| --------- | -----
name | string - name of the plan             | yes        |
identifier | string - identifier of the plan | yes        |
interval | string - interval of the plan      | yes        | 'Ciclo do plano (Número inteiro maior que 0). Intervalo até a próxima cobrança.'
interval_type | string - interval_type of the plan      | yes        | 'Tipo de interval ("weeks" ou "months").'
value_cents | string - value_cents of the plan      | yes        | 'Preço do plano em centavos'
payable_with | string - payable_with of the plan      | no        | default its credit_card


> The above command returns JSON structured like this:

```json
{
    "id": "593C92165AF44493B65DE17A216C76D6",
    "name": "Plano Básico",
    "identifier": "basic_plan",
    "interval": 1,
    "interval_type": "months",
    "created_at": "2014-04-23T17:14:15-03:00",
    "updated_at": "2014-04-23T17:14:15-03:00",
    "prices": [{
        "created_at": "2014-04-23T17:14:15-03:00",
        "currency": "BRL",
        "id": "F465EE77AC424DA2B075133C96FF10CA",
        "plan_id": "593C92165AF44493B65DE17A216C76D6",
        "updated_at": "2014-04-23T17:14:15-03:00",
        "value_cents": 1000
    }],
    "features": [{
        "created_at": "2014-04-23T17:14:15-03:00",
        "id": "6101C66D06564E3DB834BCE235A587A6",
        "identifier": "users",
        "important": null,
        "name": "Número de Usuários",
        "plan_id": "593C92165AF44493B65DE17A216C76D6",
        "position": 1,
        "updated_at": "2014-04-23T17:14:15-03:00",
        "value": 10
    }]
}
```
## Update a Plan  (USE IUGU DASHBOARD)
### HTTP Request
`PUT http://localhost:3000/v1/plans/:id`

This endpoint updates a plan.

```shell
curl -X PUT -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/plans/593C92165AF44493B65DE17A216C76D6" \
  -d '{"identifier" :"basic_plan_new"
    }'
```


Parameter | Description                              | Required? | Observation
--------- | -----------------------------------------| --------- | -----
name | string - name of the plan             | yes        |
identifier | string - identifier of the plan | yes        |
interval | string - interval of the plan      | yes        | 'Ciclo do plano (Número inteiro maior que 0). Intervalo até a próxima cobrança.'
interval_type | string - interval_type of the plan      | yes        | 'Tipo de interval ("weeks" ou "months").'
value_cents | string - value_cents of the plan      | yes        | 'Preço do plano em centavos'
payable_with | string - payable_with of the plan      | no        | default its credit_card


> The above command returns JSON structured like this:

```json
{
    "id": "593C92165AF44493B65DE17A216C76D6",
    "name": "Plano Básico",
    "identifier": "basic_plan_new",
    "interval": 1,
    "interval_type": "months",
    "created_at": "2014-04-23T17:14:15-03:00",
    "updated_at": "2014-04-23T17:14:15-03:00",
    "prices": [{
        "created_at": "2014-04-23T17:14:15-03:00",
        "currency": "BRL",
        "id": "F465EE77AC424DA2B075133C96FF10CA",
        "plan_id": "593C92165AF44493B65DE17A216C76D6",
        "updated_at": "2014-04-23T17:14:15-03:00",
        "value_cents": 1000
    }],
    "features": [{
        "created_at": "2014-04-23T17:14:15-03:00",
        "id": "6101C66D06564E3DB834BCE235A587A6",
        "identifier": "users",
        "important": null,
        "name": "Número de Usuários",
        "plan_id": "593C92165AF44493B65DE17A216C76D6",
        "position": 1,
        "updated_at": "2014-04-23T17:14:15-03:00",
        "value": 10
    }]
}
```
## Delete a Plan  (USE IUGU DASHBOARD)
### HTTP Request
`DELETE http://localhost:3000/v1/plans/:id`

This endpoint deletes a plan.

```shell
curl -X DELETE -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/plans/593C92165AF44493B65DE17A216C76D6"
```



> The above command returns JSON structured like this:

```json
{
    "id": "593C92165AF44493B65DE17A216C76D6",
    "name": "Plano Básico",
    "identifier": "basic_plan",
    "interval": 1,
    "interval_type": "months",
    "created_at": "2014-04-23T17:14:15-03:00",
    "updated_at": "2014-04-23T17:14:15-03:00",
    "prices": [{
        "created_at": "2014-04-23T17:14:15-03:00",
        "currency": "BRL",
        "id": "F465EE77AC424DA2B075133C96FF10CA",
        "plan_id": "593C92165AF44493B65DE17A216C76D6",
        "updated_at": "2014-04-23T17:14:15-03:00",
        "value_cents": 1000
    }],
    "features": [{
        "created_at": "2014-04-23T17:14:15-03:00",
        "id": "6101C66D06564E3DB834BCE235A587A6",
        "identifier": "users",
        "important": null,
        "name": "Número de Usuários",
        "plan_id": "593C92165AF44493B65DE17A216C76D6",
        "position": 1,
        "updated_at": "2014-04-23T17:14:15-03:00",
        "value": 10
    }]
}
```
## Get a plan by its id
### HTTP Request
`GET http://localhost:3000/v1/plans/:id`

This endpoint get a plan.

```shell
curl -X GET -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/plans/593C92165AF44493B65DE17A216C76D6"
```



> The above command returns JSON structured like this:

```json
{
    "id": "593C92165AF44493B65DE17A216C76D6",
    "name": "Plano Básico",
    "identifier": "basic_plan",
    "interval": 1,
    "interval_type": "months",
    "created_at": "2014-04-23T17:14:15-03:00",
    "updated_at": "2014-04-23T17:14:15-03:00",
    "prices": [{
        "created_at": "2014-04-23T17:14:15-03:00",
        "currency": "BRL",
        "id": "F465EE77AC424DA2B075133C96FF10CA",
        "plan_id": "593C92165AF44493B65DE17A216C76D6",
        "updated_at": "2014-04-23T17:14:15-03:00",
        "value_cents": 1000
    }],
    "features": [{
        "created_at": "2014-04-23T17:14:15-03:00",
        "id": "6101C66D06564E3DB834BCE235A587A6",
        "identifier": "users",
        "important": null,
        "name": "Número de Usuários",
        "plan_id": "593C92165AF44493B65DE17A216C76D6",
        "position": 1,
        "updated_at": "2014-04-23T17:14:15-03:00",
        "value": 10
    }]
}
```
## Get a plan by its identifier
### HTTP Request
`GET http://localhost:3000/v1/plans/identifier/:identifier`

This endpoint get a plan by its identifier.

```shell
curl -X GET -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/plans/identifier/basic_plan"
```



> The above command returns JSON structured like this:

```json
{
    "id": "593C92165AF44493B65DE17A216C76D6",
    "name": "Plano Básico",
    "identifier": "basic_plan",
    "interval": 1,
    "interval_type": "months",
    "created_at": "2014-04-23T17:14:15-03:00",
    "updated_at": "2014-04-23T17:14:15-03:00",
    "prices": [{
        "created_at": "2014-04-23T17:14:15-03:00",
        "currency": "BRL",
        "id": "F465EE77AC424DA2B075133C96FF10CA",
        "plan_id": "593C92165AF44493B65DE17A216C76D6",
        "updated_at": "2014-04-23T17:14:15-03:00",
        "value_cents": 1000
    }],
    "features": [{
        "created_at": "2014-04-23T17:14:15-03:00",
        "id": "6101C66D06564E3DB834BCE235A587A6",
        "identifier": "users",
        "important": null,
        "name": "Número de Usuários",
        "plan_id": "593C92165AF44493B65DE17A216C76D6",
        "position": 1,
        "updated_at": "2014-04-23T17:14:15-03:00",
        "value": 10
    }]
}
```

## Get all plans
### HTTP Request
`GET http://localhost:3000/v1/plans`

This endpoint get all plans.

```shell
curl -X GET -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/plans"
```

> The above command returns JSON structured like this:

```json
{
    "totalItems": 1,
    "items": [{
        "id": "593C92165AF44493B65DE17A216C76D6",
        "name": "Plano Básico",
        "identifier": "basic_plan",
        "interval": 1,
        "interval_type": "months",
        "created_at": "2014-04-23T17:14:15-03:00",
        "updated_at": "2014-04-23T17:19:46-03:00",
        "prices": [{
            "created_at": "2014-04-23T17:14:15-03:00",
            "currency": "BRL",
            "id": "F465EE77AC424DA2B075133C96FF10CA",
            "updated_at": "2014-04-23T17:14:15-03:00",
            "value_cents": 1000
        }]
    }]
}
```
# Subscription
## Create a Subscription
### HTTP Request
`POST http://localhost:3000/v1/subscriptions`

This endpoint creates a subscription.

```shell
curl -X POST -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/subscriptions" \
  -d '{"customer_id":"FF3149CE52CB4A789925F154B48"}'
```

Parameter              | Description                              | Required? | Observation
---------              | -----------------------------------------| ---------- | -----
plan_identifier        | string - identifier of the plan          | no        |
customer_id            | string - client id                       | yes        |
expires_at             | string - expiration date                 | no        | Data de Expiração "DD-MM-AAAA". (Data da primeira cobrança, as próximas datas de cobrança dependem do "intervalo" do plano vinculado).
only_on_charge_success | boolean - change on success      | no        | Apenas Cria a Assinatura se a Cobrança for bem sucedida. Isso só funciona caso o cliente já tenha uma forma de pagamento padrão cadastrada. Não enviar "expires_at". (Default é false)
ignore_due_email       | boolean - ignore due email         | no        |  (Default é false)
payable_with           | string - options of payment        | no         |  (Default é credit_card)


> The above command returns JSON structured like this:

```json
{
    "id": "ECF36F9AAF374D76A48646EDE8FE806D",
    "suspended": false,
    "plan_identifier": "id1",
    "price_cents": 200,
    "currency": "BRL",
    "features": {
        "feat": {
            "name": "Feature",
            "value": 0
        }
    },
    "expires_at": null,
    "created_at": "2013-11-19T11:24:29-02:00",
    "updated_at": "2013-11-19T11:24:43-02:00",
    "customer_name": "Nome do Cliente",
    "customer_email": "email@email.com",
    "cycled_at": null,
    "credits_min": 0,
    "credits_cycle": null,
    "customer_id": "FF3149CE52CB4A789925F154B489BFDD",
    "plan_name": "plan1",
    "customer_ref": "Nome do Cliente",
    "plan_ref": "plan1",
    "active": true,
    "in_trial": null,
    "credits": 0,
    "credits_based": false,
    "recent_invoices": null,
    "subitems": [{
        "id": "6D518D88B33F48FEA8964D5573E220D3",
        "description": "Item um",
        "quantity": 1,
        "price_cents": 1000,
        "price": "R$ 10,00",
        "total": "R$ 10,00"
    }],
    "logs": [{
        "id": "477388CC4C024520B552641724A62970",
        "description": "Fatura criada",
        "notes": "Fatura criada 1x Ativação de Assinatura: plan1 = R$ 2,00;1x Item um = R$ 10,00;",
        "created_at": "2013-11-19T11:24:43-02:00"
    }, {
        "id": "706436F169CE465B806163964A25400A",
        "description": "Assinatura Criada",
        "notes": "Assinatura Criada",
        "created_at": "2013-11-19T11:24:29-02:00"
    }],
    "custom_variables":[]
}
```
## Update a Subscription
### HTTP Request
`PUT http://localhost:3000/v1/subscriptions/:id`

This endpoint updates a subscription.

```shell
curl -X PUT -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/subscriptions/ECF36F9AAF374D76A48646EDE8FE806D" \
  -d '{"identifier" :"basic_plan_new"
    }'
```


Parameter              | Description                              | Required? | Observation
---------              | -----------------------------------------| ---------- | -----
plan_identifier        | string - identifier of the plan          | no        |
id            | string - client id                       | yes        |
expires_at             | string - expiration date                 | no        | Data de Expiração "DD-MM-AAAA". (Data da primeira cobrança, as próximas datas de cobrança dependem do "intervalo" do plano vinculado).
only_on_charge_success | boolean - change on success      | no        | Apenas Cria a Assinatura se a Cobrança for bem sucedida. Isso só funciona caso o cliente já tenha uma forma de pagamento padrão cadastrada. Não enviar "expires_at". (Default é false)
ignore_due_email       | boolean - ignore due email         | no        |  (Default é false)
payable_with           | string - options of payment        | no         |  (Default é credit_card)



> The above command returns JSON structured like this:

```json
{
    "id": "ECF36F9AAF374D76A48646EDE8FE806D",
    "suspended": true,
    "plan_identifier": "id1",
    "price_cents": 200,
    "currency": "BRL",
    "features": {
        "feat": {
            "name": "Feature",
            "value": 0
        }
    },
    "expires_at": null,
    "created_at": "2013-11-19T11:24:29-02:00",
    "updated_at": "2013-11-19T11:24:43-02:00",
    "customer_name": "Nome do Cliente",
    "customer_email": "email@email.com",
    "cycled_at": null,
    "credits_min": 0,
    "credits_cycle": null,
    "customer_id": "FF3149CE52CB4A789925F154B489BFDD",
    "plan_name": "plan1",
    "customer_ref": "Nome do Cliente",
    "plan_ref": "plan1",
    "active": true,
    "in_trial": null,
    "credits": 0,
    "credits_based": false,
    "recent_invoices": null,
    "subitems": [{
        "id": "6D518D88B33F48FEA8964D5573E220D3",
        "description": "Item um",
        "quantity": 1,
        "price_cents": 1000,
        "price": "R$ 10,00",
        "total": "R$ 10,00"
    }],
    "logs": [{
        "id": "477388CC4C024520B552641724A62970",
        "description": "Fatura criada",
        "notes": "Fatura criada 1x Ativação de Assinatura: plan1 = R$ 2,00;1x Item um = R$ 10,00;",
        "created_at": "2013-11-19T11:24:43-02:00"
    }, {
        "id": "706436F169CE465B806163964A25400A",
        "description": "Assinatura Criada",
        "notes": "Assinatura Criada",
        "created_at": "2013-11-19T11:24:29-02:00"
    }],
    "custom_variables":[]
}
```
## Delete a Subscription
### HTTP Request
`DELETE http://localhost:3000/v1/subscriptions/:id`

This endpoint deletes a subscription.

```shell
curl -X DELETE -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/subscriptions/ECF36F9AAF374D76A48646EDE8FE806D"
```



> The above command returns JSON structured like this:

```json
{
    "id": "ECF36F9AAF374D76A48646EDE8FE806D",
    "suspended": true,
    "plan_identifier": "id1",
    "price_cents": 200,
    "currency": "BRL",
    "features": {
        "feat": {
            "name": "Feature",
            "value": 0
        }
    },
    "expires_at": null,
    "created_at": "2013-11-19T11:24:29-02:00",
    "updated_at": "2013-11-19T11:24:43-02:00",
    "customer_name": "Nome do Cliente",
    "customer_email": "email@email.com",
    "cycled_at": null,
    "credits_min": 0,
    "credits_cycle": null,
    "customer_id": "FF3149CE52CB4A789925F154B489BFDD",
    "plan_name": "plan1",
    "customer_ref": "Nome do Cliente",
    "plan_ref": "plan1",
    "active": true,
    "in_trial": null,
    "credits": 0,
    "credits_based": false,
    "recent_invoices": null,
    "subitems": [{
        "id": "6D518D88B33F48FEA8964D5573E220D3",
        "description": "Item um",
        "quantity": 1,
        "price_cents": 1000,
        "price": "R$ 10,00",
        "total": "R$ 10,00"
    }],
    "logs": [{
        "id": "477388CC4C024520B552641724A62970",
        "description": "Fatura criada",
        "notes": "Fatura criada 1x Ativação de Assinatura: plan1 = R$ 2,00;1x Item um = R$ 10,00;",
        "created_at": "2013-11-19T11:24:43-02:00"
    }, {
        "id": "706436F169CE465B806163964A25400A",
        "description": "Assinatura Criada",
        "notes": "Assinatura Criada",
        "created_at": "2013-11-19T11:24:29-02:00"
    }],
    "custom_variables":[]
}
```
## Get a subscription by its id
### HTTP Request
`GET http://localhost:3000/v1/subscriptions/:id`

This endpoint get a subscription.

```shell
curl -X GET -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/subscriptions/ECF36F9AAF374D76A48646EDE8FE806D"
```



> The above command returns JSON structured like this:

```json
{
    "id": "ECF36F9AAF374D76A48646EDE8FE806D",
    "suspended": false,
    "plan_identifier": "id1",
    "price_cents": 200,
    "currency": "BRL",
    "features": {
        "feat": {
            "name": "Feature",
            "value": 0
        }
    },
    "expires_at": null,
    "created_at": "2013-11-19T11:24:29-02:00",
    "updated_at": "2013-11-19T11:24:43-02:00",
    "customer_name": "Nome do Cliente",
    "customer_email": "email@email.com",
    "cycled_at": null,
    "credits_min": 0,
    "credits_cycle": null,
    "customer_id": "FF3149CE52CB4A789925F154B489BFDD",
    "plan_name": "plan1",
    "customer_ref": "Nome do Cliente",
    "plan_ref": "plan1",
    "active": true,
    "in_trial": null,
    "credits": 0,
    "credits_based": false,
    "recent_invoices": null,
    "subitems": [{
        "id": "6D518D88B33F48FEA8964D5573E220D3",
        "description": "Item um",
        "quantity": 1,
        "price_cents": 1000,
        "price": "R$ 10,00",
        "total": "R$ 10,00"
    }],
    "logs": [{
        "id": "477388CC4C024520B552641724A62970",
        "description": "Fatura criada",
        "notes": "Fatura criada 1x Ativação de Assinatura: plan1 = R$ 2,00;1x Item um = R$ 10,00;",
        "created_at": "2013-11-19T11:24:43-02:00"
    }, {
        "id": "706436F169CE465B806163964A25400A",
        "description": "Assinatura Criada",
        "notes": "Assinatura Criada",
        "created_at": "2013-11-19T11:24:29-02:00"
    }],
    "custom_variables":[]
}
```
## Activate/reactivate a subscription
### HTTP Request
`POST http://localhost:3000/v1/subscriptions/:id/reactivate`

This endpoint activate a subscription.

```shell
curl -X POST -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/subscriptions/ECF36F9AAF374D76A48646EDE8FE806D/reactivate"
```



> The above command returns JSON structured like this:

```json
{
    "id": "ECF36F9AAF374D76A48646EDE8FE806D",
    "suspended": false,
    "plan_identifier": "id1",
    "price_cents": 200,
    "currency": "BRL",
    "features": {
        "feat": {
            "name": "Feature",
            "value": 0
        }
    },
    "expires_at": null,
    "created_at": "2013-11-19T11:24:29-02:00",
    "updated_at": "2013-11-19T11:24:43-02:00",
    "customer_name": "Nome do Cliente",
    "customer_email": "email@email.com",
    "cycled_at": null,
    "credits_min": 0,
    "credits_cycle": null,
    "customer_id": "FF3149CE52CB4A789925F154B489BFDD",
    "plan_name": "plan1",
    "customer_ref": "Nome do Cliente",
    "plan_ref": "plan1",
    "active": true,
    "in_trial": null,
    "credits": 0,
    "credits_based": false,
    "recent_invoices": null,
    "subitems": [{
        "id": "6D518D88B33F48FEA8964D5573E220D3",
        "description": "Item um",
        "quantity": 1,
        "price_cents": 1000,
        "price": "R$ 10,00",
        "total": "R$ 10,00"
    }],
    "logs": [{
        "id": "477388CC4C024520B552641724A62970",
        "description": "Fatura criada",
        "notes": "Fatura criada 1x Ativação de Assinatura: plan1 = R$ 2,00;1x Item um = R$ 10,00;",
        "created_at": "2013-11-19T11:24:43-02:00"
    }, {
        "id": "706436F169CE465B806163964A25400A",
        "description": "Assinatura Criada",
        "notes": "Assinatura Criada",
        "created_at": "2013-11-19T11:24:29-02:00"
    }],
    "custom_variables":[]
}
```
## Suspend a subscription
### HTTP Request
`POST http://localhost:3000/v1/subscriptions/:id/suspend`

This endpoint suspend a subscription.

```shell
curl -X POST -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/subscriptions/ECF36F9AAF374D76A48646EDE8FE806D/suspend"
```

> The above command returns JSON structured like this:

```json
{
    "id": "ECF36F9AAF374D76A48646EDE8FE806D",
    "suspended": true,
    "plan_identifier": "id1",
    "price_cents": 200,
    "currency": "BRL",
    "features": {
        "feat": {
            "name": "Feature",
            "value": 0
        }
    },
    "expires_at": null,
    "created_at": "2013-11-19T11:24:29-02:00",
    "updated_at": "2013-11-19T11:24:43-02:00",
    "customer_name": "Nome do Cliente",
    "customer_email": "email@email.com",
    "cycled_at": null,
    "credits_min": 0,
    "credits_cycle": null,
    "customer_id": "FF3149CE52CB4A789925F154B489BFDD",
    "plan_name": "plan1",
    "customer_ref": "Nome do Cliente",
    "plan_ref": "plan1",
    "active": true,
    "in_trial": null,
    "credits": 0,
    "credits_based": false,
    "recent_invoices": null,
    "subitems": [{
        "id": "6D518D88B33F48FEA8964D5573E220D3",
        "description": "Item um",
        "quantity": 1,
        "price_cents": 1000,
        "price": "R$ 10,00",
        "total": "R$ 10,00"
    }],
    "logs": [{
        "id": "477388CC4C024520B552641724A62970",
        "description": "Fatura criada",
        "notes": "Fatura criada 1x Ativação de Assinatura: plan1 = R$ 2,00;1x Item um = R$ 10,00;",
        "created_at": "2013-11-19T11:24:43-02:00"
    }, {
        "id": "706436F169CE465B806163964A25400A",
        "description": "Assinatura Criada",
        "notes": "Assinatura Criada",
        "created_at": "2013-11-19T11:24:29-02:00"
    }],
    "custom_variables":[]
}
```

## Get all subscriptions
### HTTP Request
`GET http://localhost:3000/v1/subscriptions`

This endpoint get all subscriptions.

```shell
curl -X GET -H "Accept: Application/json" -H "Content-Type: application/json"\
 "http://localhost:3000/v1/subscriptions"
```

> The above command returns JSON structured like this:

```json
{
    "facets": {
        "suspended": {
            "_type": "filter",
            "count": 1
        },
        "active": {
            "_type": "filter",
            "count": 1
        },
        "due": {
            "_type": "filter",
            "count": 1
        }
    },
    "totalItems": 3,
    "items": [{
        "id": "ECF36F9AAF374D76A48646EDE8FE806D",
        "suspended": false,
        "plan_identifier": "id2",
        "price_cents": 200,
        "currency": "BRL",
        "features": {
            "feat": {
                "name": "Feature",
                "value": 10
            }
        },
        "expires_at": null,
        "created_at": "2013-11-19T11:24:29-02:00",
        "updated_at": "2013-11-19T11:24:43-02:00",
        "customer_name": "Nome do Cliente",
        "customer_email": "email@email.com",
        "cycled_at": null,
        "customer_id": "FF3149CE52CB4A789925F154B489BFDD",
        "plan_name": "plan1",
        "customer_ref": "Nome do Cliente",
        "plan_ref": "plan1",
        "active": true,
        "in_trial": null,
        "recent_invoices": null,
        "subitems": [{
            "id": "6D518D88B33F48FEA8964D5573E220D3",
            "description": "Item um",
            "quantity": 1,
            "price_cents": 1000,
            "price": "R$ 10,00",
            "total": "R$ 10,00"
        }],
        "logs": [{
            "id": "477388CC4C024520B552641724A62970",
            "description": "Fatura criada",
            "notes": "Fatura criada 1x Ativação de Assinatura: plan1 = R$ 2,00;1x Item um = R$ 10,00;",
            "created_at": "2013-11-19T11:24:43-02:00"
        }, {
            "id": "706436F169CE465B806163964A25400A",
            "description": "Assinatura Criada",
            "notes": "Assinatura Criada",
            "created_at": "2013-11-19T11:24:29-02:00"
        }]
    }, {
        "id": "ECF36F9AAF374D76A48646EDE8FE806D",
        "suspended": false,
        "plan_identifier": "id2",
        "price_cents": 200,
        "currency": "BRL",
        "features": {
            "feat": {
                "name": "Feature",
                "value": 10
            }
        },
        "expires_at": null,
        "created_at": "2013-11-19T11:24:29-02:00",
        "updated_at": "2013-11-19T11:24:43-02:00",
        "customer_name": "Nome do Cliente",
        "customer_email": "email@email.com",
        "cycled_at": null,
        "customer_id": "FF3149CE52CB4A789925F154B489BFDD",
        "plan_name": "plan1",
        "customer_ref": "Nome do Cliente",
        "plan_ref": "plan1",
        "active": true,
        "in_trial": null,
        "recent_invoices": null,
        "subitems": [{
            "id": "6D518D88B33F48FEA8964D5573E220D3",
            "description": "Item um",
            "quantity": 1,
            "price_cents": 1000,
            "price": "R$ 10,00",
            "total": "R$ 10,00"
        }],
        "logs": [{
            "id": "477388CC4C024520B552641724A62970",
            "description": "Fatura criada",
            "notes": "Fatura criada 1x Ativação de Assinatura: plan1 = R$ 2,00;1x Item um = R$ 10,00;",
            "created_at": "2013-11-19T11:24:43-02:00"
        }, {
            "id": "706436F169CE465B806163964A25400A",
            "description": "Assinatura Criada",
            "notes": "Assinatura Criada",
            "created_at": "2013-11-19T11:24:29-02:00"
        }]
    }, {
        "id": "ECF36F9AAF374D76A48646EDE8FE806D",
        "suspended": false,
        "plan_identifier": "id2",
        "price_cents": 200,
        "currency": "BRL",
        "features": {
            "feat": {
                "name": "Feature",
                "value": 10
            }
        },
        "expires_at": null,
        "created_at": "2013-11-19T11:24:29-02:00",
        "updated_at": "2013-11-19T11:24:43-02:00",
        "customer_name": "Nome do Cliente",
        "customer_email": "email@email.com",
        "cycled_at": null,
        "customer_id": "FF3149CE52CB4A789925F154B489BFDD",
        "plan_name": "plan1",
        "customer_ref": "Nome do Cliente",
        "plan_ref": "plan1",
        "active": true,
        "in_trial": null,
        "recent_invoices": null,
        "subitems": [{
            "id": "6D518D88B33F48FEA8964D5573E220D3",
            "description": "Item um",
            "quantity": 1,
            "price_cents": 1000,
            "price": "R$ 10,00",
            "total": "R$ 10,00"
        }],
        "logs": [{
            "id": "477388CC4C024520B552641724A62970",
            "description": "Fatura criada",
            "notes": "Fatura criada 1x Ativação de Assinatura: plan1 = R$ 2,00;1x Item um = R$ 10,00;",
            "created_at": "2013-11-19T11:24:43-02:00"
        }, {
            "id": "706436F169CE465B806163964A25400A",
            "description": "Assinatura Criada",
            "notes": "Assinatura Criada",
            "created_at": "2013-11-19T11:24:29-02:00"
        }]
    }]
}
```

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
