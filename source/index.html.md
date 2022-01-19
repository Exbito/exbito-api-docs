---
title: Exbito API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - python
  - javascript

toc_footers:
  - <a href='https://exbito.com/'>Exbito website</a>
  - <a href='https://app.exbito.com/register'>Exbito Web App</a>
  - <a href='https://play.google.com/store/apps/details?id=com.exbito.app'>Exbito Android App</a>
  - <a href='https://exbito.com/fees'>Exchange fee rates</a>
includes:
  - websocket
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Exbito API
---

# Introduction

Welcome to the Exbito API! You can use our API to access Exbito API endpoints.

# Authentication

Exbito uses `API_KEY` and `API_SECRET` keys to allow access to the API. You can register a new API key at the [profile settings -> API keys](https://app.exbito.com/more/api).

Exbito expects for the both `API_KEY` and `API_SECRET` to be included in all API requests to the server in a header that looks like the following:

```
X-Api-Key: MY_API_KEY
X-Api-Secret: MY_API_SECRET
```

<aside class="notice">
You must replace <code>MY_API_KEY</code> and <code>MY_API_SECRET</code> with your personal API key and secret.
</aside>

<aside class="notice">
Please NEVER share your API secret with anyone!
</aside>

# Public endpoints

## Get All Markets

```python
import requests

requests.request(
  'GET',
  f'https://exbito.com/apiv2/markets'
).json()
```

```shell
curl "https://exbito.com/apiv2/markets"
```

```javascript
const axios = require('axios');

axios.get('https://exbito.com/apiv2/markets')
```

> The above command returns JSON structured like this:

```json
[
  {
    "name": "BTC_USDT",
    "minAmount": "0.00001000",
    "baseCurrencySymbol": "BTC",
    "quoteCurrencySymbol": "USDT",
    "buyAmountMin": "0.00010000",
    "buyAmountMax": "10.00000000",
    "sellAmountMin": "0.00010000",
    "sellAmountMax": "10.00000000",
    "quoteMin": "10.000000",
    "quoteMax": "10000000.000000",
    "isVisible": true,
    "isEnable": true,
    "defaultDepthInterval": "10.000000",
    "priceStep": "1.000000",
    "amountStep": "0.00001000",
    "depthIntervalList": [
      "0",
      "10.000000",
      "100.000000",
      "1000.000000"
    ]
  },
  {
    "name": "ETH_USDT",
    "minAmount": "0.000100000000000000",
    "baseCurrencySymbol": "ETH",
    "quoteCurrencySymbol": "USDT",
    "buyAmountMin": "0.001000000000000000",
    "buyAmountMax": "100.000000000000000000",
    "sellAmountMin": "0.001000000000000000",
    "sellAmountMax": "100.000000000000000000",
    "quoteMin": "10.000000",
    "quoteMax": "10000000.000000",
    "isVisible": true,
    "isEnable": true,
    "defaultDepthInterval": "1.000000",
    "priceStep": "1.000000",
    "amountStep": "0.000100000000000000",
    "depthIntervalList": [
      "0",
      "1.000000",
      "10.000000",
      "100.000000"
    ]
  }
]
```

This endpoint retrieves all markets.

### HTTP Request

`GET https://exbito.com/apiv2/markets`

<aside class="notice">
The rate-limit for this endpoint is 10 req/min.
</aside>

## Get a Specific Market

```python
import requests

requests.request(
  'GET',
  f'https://exbito.com/apiv2/markets/BTC_USDT'
).json()
```

```shell
curl "https://exbito.com/apiv2/markets/BTC_USDT"
```

```javascript
const axios = require('axios');

axios.get('https://exbito.com/apiv2/markets/BTC_USDT')
```

> The above command returns JSON structured like this:

```json
[
  {
    "name": "BTC_USDT",
    "minAmount": "0.00001000",
    "baseCurrencySymbol": "BTC",
    "quoteCurrencySymbol": "USDT",
    "buyAmountMin": "0.00010000",
    "buyAmountMax": "10.00000000",
    "sellAmountMin": "0.00010000",
    "sellAmountMax": "10.00000000",
    "quoteMin": "10.000000",
    "quoteMax": "10000000.000000",
    "isVisible": true,
    "isEnable": true,
    "defaultDepthInterval": "10.000000",
    "priceStep": "1.000000",
    "amountStep": "0.00001000",
    "depthIntervalList": [
      "0",
      "10.000000",
      "100.000000",
      "1000.000000"
    ]
  }
]
```

This endpoint retrieves one single markets.

### HTTP Request

`GET https://exbito.com/apiv2/markets`

<aside class="notice">
The rate-limit for this endpoint is 10 req/min.
</aside>

## Get All Currencies

```python
import requests

requests.request(
  'GET',
  f'https://exbito.com/apiv2/currencies'
).json()
```

```shell
curl "https://exbito.com/apiv2/currencies"
```

```javascript
const axios = require('axios');

axios.get('https://exbito.com/apiv2/currencies')
```

> The above command returns JSON structured like this:

```json
[
  {
    "name": "BTC_USDT",
    "minAmount": "0.00001000",
    "baseCurrencySymbol": "BTC",
    "quoteCurrencySymbol": "USDT",
    "buyAmountMin": "0.00010000",
    "buyAmountMax": "10.00000000",
    "sellAmountMin": "0.00010000",
    "sellAmountMax": "10.00000000",
    "quoteMin": "10.000000",
    "quoteMax": "10000000.000000",
    "isVisible": true,
    "isEnable": true,
    "defaultDepthInterval": "10.000000",
    "priceStep": "1.000000",
    "amountStep": "0.00001000",
    "depthIntervalList": [
      "0",
      "10.000000",
      "100.000000",
      "1000.000000"
    ]
  },
  {
    "name": "ETH_USDT",
    "minAmount": "0.000100000000000000",
    "baseCurrencySymbol": "ETH",
    "quoteCurrencySymbol": "USDT",
    "buyAmountMin": "0.001000000000000000",
    "buyAmountMax": "100.000000000000000000",
    "sellAmountMin": "0.001000000000000000",
    "sellAmountMax": "100.000000000000000000",
    "quoteMin": "10.000000",
    "quoteMax": "10000000.000000",
    "isVisible": true,
    "isEnable": true,
    "defaultDepthInterval": "1.000000",
    "priceStep": "1.000000",
    "amountStep": "0.000100000000000000",
    "depthIntervalList": [
      "0",
      "1.000000",
      "10.000000",
      "100.000000"
    ]
  }
]
```

This endpoint retrieves all currencies.

### HTTP Request

`GET https://exbito.com/apiv2/markets`

<aside class="notice">
The rate-limit for this endpoint is 10 req/min.
</aside>

# Private endpoints

## Get All Markets

```python
import requests

requests.request(
  'GET',
  f'https://exbito.com/apiv2/markets',
  headers={'X-Api-Key': MY_API_KEY, 'X-Api-Secret': MY_API_SECRET}
).json()
```

```shell
curl "https://exbito.com/apiv2/markets" \
  -H "X-Api-Key: $MY_API_KEY" \
  -H "X-Api-Secret: $MY_API_SECRET"
```

```javascript
const axios = require('axios');

axios.get('https://exbito.com/apiv2/markets', {
  headers: {
    'X-Api-Key': MY_API_KEY,
    'X-Api-Secret': MY_API_SECRET,
  }
})
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

