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

## Get Market's Last Price

```python
import requests

requests.request(
  'GET',
  f'https://api.exbito.com/apiv2/markets/BTC_USDT/last'
).json()
```

```shell
curl "https://api.exbito.com/apiv2/markets/BTC_USDT/last"
```

```javascript
const axios = require('axios');

axios.get('https://api.exbito.com/apiv2/markets/BTC_USDT/last')
```

> The above command returns JSON structured like this:

```json
{
  "name": "BTC_USDT",
  "price": "38265.840000"
}
```

This endpoints returns the latest price of a market.

<aside class="notice">
This api return the realtime/fresh data.
</aside>

### HTTP Request

`GET https://api.exbito.com/apiv2/markets/<MARKET_NAME>/last`

### URL Parameters

Parameter | Description
--------- | -----------
MARKET_NAME | The Symbol of the market (fully uppercase, underscore delimited) (Example: BTC_USDT)

## Get Market's Status

```python
import requests

requests.request(
  'GET',
  f'https://api.exbito.com/apiv2/markets/BTC_USDT/status'
).json()
```

```shell
curl "https://api.exbito.com/apiv2/markets/BTC_USDT/status"
```

```javascript
const axios = require('axios');

axios.get('https://api.exbito.com/apiv2/markets/BTC_USDT/status')
```

> The above command returns JSON structured like this:

```json
{
  "open": "37041.010000",
  "high": "38706.290000",
  "low": "36863.990000",
  "close": "38287.790000",
  "volume": "1.34927867",
  "deal": "51058.168482",
  "last": "38287.790000",
  "period": 86400
}
```

This endpoints returns the status of a market.

### HTTP Request

`GET https://api.exbito.com/apiv2/markets/<MARKET_NAME>/status`

### URL Parameters

Parameter | Description
--------- | -----------
MARKET_NAME | The Symbol of the market (fully uppercase, underscore delimited) (Example: BTC_USDT)

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
period | - | The period, in seconds

## Get Market's KLine (e.g. Candlestick / OHLC)

```python
import requests

requests.request(
  'GET',
  f'https://api.exbito.com/apiv2/markets/BTC_USDT/kline?start=1641820000&end=1642520000&interval=3600'
).json()
```

```shell
curl "https://api.exbito.com/apiv2/markets/BTC_USDT/kline?start=1641820000&end=1642520000&interval=3600"
```

```javascript
const axios = require('axios');

axios.get('https://api.exbito.com/apiv2/markets/BTC_USDT/kline?start=1641820000&end=1642520000&interval=3600')
```

> The above command returns JSON structured like this:

```json
[
  {
    "market": "BTC_USDT",
    "time": 1641819600,
    "o": "40923.360000",
    "h": "41046.680000",
    "l": "40757.970000",
    "c": "40757.970000",
    "volume": "0.06765753",
    "amount": "0.27665754"
  },
  {
    "market": "BTC_USDT",
    "time": 1641823200,
    "o": "40778.000000",
    "h": "41185.080000",
    "l": "39468.000000",
    "c": "40768.530000",
    "volume": "0.07010710",
    "amount": "0.28329002"
  }
]
```

This endpoints returns the kline of a market. (e.g. Candlestick / OHLC)

### HTTP Request

`GET https://api.exbito.com/apiv2/markets/<MARKET_NAME>/kline`

### URL Parameters

Parameter | Description
--------- | -----------
MARKET_NAME | The Symbol of the market (fully uppercase, underscore delimited) (Example: BTC_USDT)

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
interval | - | The duration of each candle, in seconds (Sample: 3600) MUST BE a multiple of 60
start | - | The epoch time of the start of the period (Sample: 1641820000)
end | - | The epoch time of the end of the period (Sample: 1642520000)

<aside class="warning">
This endpoint might not return the fresh/relatime data. Please do not use this endpoint for the realtime usages.
</aside>

<aside class="warning">
Pleas note that:

* Interval MUST BE a multiple of 60
* The maximum candles number is 1000 (You have to adjust the start and the end parameters to meet this limit)
* The start and end timestamps are base on UTC timezone and [UnixTime](https://en.wikipedia.org/wiki/Unix_time)
  standard.
* The `end` value must be greater than `start`
* The `end` , `start` and `interval` must be all positive integer

</aside>
