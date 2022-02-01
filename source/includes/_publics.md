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
Pleas note that the `interval` MUST BE a multiple of 60
</aside>

<aside class="warning">
The maximum candles number is 1000 (You have to adjust the start and the end parameters to meet this limit)
</aside>

<aside class="warning">
The start and end timestamps are base on UTC timezone and [UnixTime](https://en.wikipedia.org/wiki/Unix_time) standard.
</aside>

<aside class="warning">
The `end` value must be greater than `start`
</aside>

<aside class="warning">
The `end` , `start` and `interval` must be all positive integer
</aside>

## Get Market's Order Book (Depth)

```python
import requests

requests.request(
  'GET',
  f'https://api.exbito.com/apiv2/markets/BTC_USDT/depth?interval=0&limit=10'
).json()
```

```shell
curl "https://api.exbito.com/apiv2/markets/BTC_USDT/depth?interval=0&limit=10"
```

```javascript
const axios = require('axios');

axios.get('https://api.exbito.com/apiv2/markets/BTC_USDT/depth?interval=0&limit=10')
```

> The above command returns JSON structured like this:

```json
{
  "asks": [
    {
      "price": "38529.000000",
      "amount": "0.00105000"
    },
    {
      "price": "38583.000000",
      "amount": "0.00098130"
    },
    {
      "price": "38723.000000",
      "amount": "0.00160400"
    },
    {
      "price": "38770.000000",
      "amount": "0.00194380"
    },
    {
      "price": "38979.000000",
      "amount": "0.01766240"
    },
    {
      "price": "38995.000000",
      "amount": "0.02932440"
    },
    {
      "price": "39076.000000",
      "amount": "0.23761600"
    },
    {
      "price": "39077.000000",
      "amount": "0.00156360"
    },
    {
      "price": "39110.000000",
      "amount": "0.40320530"
    },
    {
      "price": "39122.000000",
      "amount": "0.08285070"
    }
  ],
  "bids": [
    {
      "price": "38148.000000",
      "amount": "0.00131280"
    },
    {
      "price": "38138.000000",
      "amount": "0.00135230"
    },
    {
      "price": "37745.000000",
      "amount": "0.00155740"
    },
    {
      "price": "37704.000000",
      "amount": "0.00200920"
    },
    {
      "price": "37658.000000",
      "amount": "0.02932210"
    },
    {
      "price": "37638.000000",
      "amount": "0.01766010"
    },
    {
      "price": "37604.000000",
      "amount": "0.23756770"
    },
    {
      "price": "37595.000000",
      "amount": "0.04914760"
    },
    {
      "price": "37592.000000",
      "amount": "0.08286670"
    },
    {
      "price": "37553.000000",
      "amount": "0.00247630"
    }
  ]
}
```

This endpoints returns the current Order Book of the market (e.g. Market Depth)

### HTTP Request

`GET https://api.exbito.com/apiv2/markets/<MARKET_NAME>/depth`

### URL Parameters

Parameter | Description
--------- | -----------
MARKET_NAME | The Symbol of the market (fully uppercase, underscore delimited) (Example: BTC_USDT)

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
interval | default_depth_interval | Aggregated the order based on the price
limit | 10 | The maximum number of records on each side (max: 100)

<aside class="notice">
This api return the realtime/fresh data.
</aside>

<aside class="warning">
If you want to get all orders, you MUST send the `0` as the `interval` parameter explicitly. Otherwise, the result will be aggregated and non-accurate.
</aside>

<aside class="warning">
The `interval` value must be formatted with the exact precision of the QuoteCurrency (For example, in `BTC_USDT` market, quote currency is `USDT`, the smallestUnitScale of the `USDT` which is retreivable from the `/currencies` endpoint, is currently `-6`, so you must send it like `10.000000`. Pleas note that the trailing zeros ARE IMPORTANT!)
</aside>
