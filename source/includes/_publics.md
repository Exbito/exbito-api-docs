# Public endpoints

## Get All Markets

```python
import requests

requests.request(
  'GET',
  f'https://api.exbito.com/apiv2/markets'
).json()
```

```shell
curl "https://api.exbito.com/apiv2/markets"
```

```javascript
const axios = require('axios');

axios.get('https://api.exbito.com/apiv2/markets')
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

`GET https://api.exbito.com/apiv2/markets`

<aside class="notice">
The rate-limit for this endpoint is 10 req/min.
</aside>

## Get a Specific Market

```python
import requests

requests.request(
  'GET',
  f'https://api.exbito.com/apiv2/markets/BTC_USDT'
).json()
```

```shell
curl "https://api.exbito.com/apiv2/markets/BTC_USDT"
```

```javascript
const axios = require('axios');

axios.get('https://api.exbito.com/apiv2/markets/BTC_USDT')
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

`GET https://api.exbito.com/apiv2/markets`

<aside class="notice">
The rate-limit for this endpoint is 10 req/min.
</aside>

## Get All Currencies

```python
import requests

requests.request(
  'GET',
  f'https://api.exbito.com/apiv2/currencies'
).json()
```

```shell
curl "https://api.exbito.com/apiv2/currencies"
```

```javascript
const axios = require('axios');

axios.get('https://api.exbito.com/apiv2/currencies')
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

`GET https://api.exbito.com/apiv2/markets`

<aside class="notice">
The rate-limit for this endpoint is 10 req/min.
</aside>

