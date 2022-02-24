# Private endpoints

## Create an Order

```python
import requests

requests.request(
  'CREATE',
  f'https://api.exbito.com/apiv2/orders',
  headers={'X-Api-Key': MY_API_KEY, 'X-Api-Secret': MY_API_SECRET},
  params={
    'marketName': 'BTC_USDT',
    'type': 'limit',
    'side': 'buy',
    'amount': '0.01234000',
    'price': '35001.000000'
  }
).json()
```

```shell
curl -X CREATE "https://api.exbito.com/apiv2/orders" -H "X-Api-Key: $MY_API_KEY" -H "X-Api-Secret: $MY_API_KEY" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -d "marketName=BTC_USDT" \
  -d "type=limit" \
  -d "side=buy" \
  -d "amount=0.01234000" \
  -d "price=35001.000000"

```

```javascript
const axios = require('axios');

axios({
  method: 'create',
  url: 'https://api.exbito.com/apiv2/orders',
  headers: {'X-Api-Key': MY_API_KEY, 'X-Api-Secret': MY_API_SECRET},
  data: {
    marketName: 'BTC_USDT',
    type: 'limit',
    side: 'buy',
    amount: '0.01234000',
    price: '35001.000000'
  }
});
```

> The above command returns JSON structured like this:

```json
{
  "id": 193710506,
  "createdAt": "2021-02-23T05:56:41.123456Z",
  "modifiedAt": "2021-02-23T05:56:41.123456Z",
  "finishedAt": None,
  "market": "BTC_USDT",
  "user": 12345,
  "type": "limit",
  "side": "buy",
  "amount": "0.01234000",
  "price": "35001",
  "takerFeeRate": "0",
  "makerFeeRate": "0",
  "isAmountAsQuote": False,
  "loadStatus": "empty"
}
```

This endpoint post a new markets.

### HTTP Request

`CREATE https://api.exbito.com/apiv2/orders`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
market | - | Name of the market
type | - | Order type (possible values: `limit`, `market`)
amount | - | The amount
price | - | Order side (possible values: `buy`, `sell`)
amountAsQuote | false | Only available for "BUY MARKET" orders. If it's true, the server will treat the `amount` as quoteCurrency.

<aside class="notice">
The rate-limit for this endpoint is 10 req/min.
</aside>

## Cancel an Order

```python
import requests

requests.request(
  'CANCEL',
  f'https://api.exbito.com/apiv2/orders/12345',
  headers={'X-Api-Key': MY_API_KEY, 'X-Api-Secret': MY_API_SECRET},
).json()
```

```shell
curl -X CANCEL "https://api.exbito.com/apiv2/orders/12345" -H "X-Api-Key: $MY_API_KEY" -H "X-Api-Secret: $MY_API_KEY"

```

```javascript
const axios = require('axios');

axios({
  method: 'cancel',
  url: 'https://api.exbito.com/apiv2/orders/12345',
  headers: {'X-Api-Key': MY_API_KEY, 'X-Api-Secret': MY_API_SECRET},
});
```

> The above command returns JSON structured like this:

```json
{
  "id": 193710506,
  "createdAt": "2021-02-23T05:56:41.123456Z",
  "modifiedAt": "2021-02-23T05:56:41.123456Z",
  "finishedAt": None,
  "market": "BTC_USDT",
  "user": 12345,
  "type": "limit",
  "side": "buy",
  "amount": "0.01234000",
  "price": "35001",
  "takerFeeRate": "0",
  "makerFeeRate": "0",
  "isAmountAsQuote": False,
  "loadStatus": "partiallyCancelled"
}
```

This endpoint cancels a pending order.

### HTTP Request

`CANCEL https://api.exbito.com/apiv2/orders/<ORDER_ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ORDER_ID | Order ID (on exbito side)

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
