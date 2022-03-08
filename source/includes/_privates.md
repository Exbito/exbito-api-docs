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
  "finishedAt": null,
  "market": "BTC_USDT",
  "user": 12345,
  "type": "limit",
  "side": "buy",
  "amount": "0.01234000",
  "price": "35001",
  "takerFeeRate": "0",
  "makerFeeRate": "0",
  "isAmountAsQuote": false,
  "loadStatus": "empty"
}
```

This endpoint post a new markets.

### HTTP Request

`CREATE https://api.exbito.com/apiv2/orders`

### Form Parameters

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
  f'https://api.exbito.com/apiv2/orders/12345?marketName=BTC_USDT',
  headers={'X-Api-Key': MY_API_KEY, 'X-Api-Secret': MY_API_SECRET},
).json()
```

```shell
curl -X CANCEL "https://api.exbito.com/apiv2/orders/12345?marketName=BTC_USDT" -H "X-Api-Key: $MY_API_KEY" -H "X-Api-Secret: $MY_API_KEY"

```

```javascript
const axios = require('axios');

axios({
  method: 'cancel',
  url: 'https://api.exbito.com/apiv2/orders/12345?marketName=BTC_USDT',
  headers: {'X-Api-Key': MY_API_KEY, 'X-Api-Secret': MY_API_SECRET},
});
```

> The above command returns JSON structured like this:

```json
{
  "id": 193710506,
  "createdAt": "2021-02-23T05:56:41.123456Z",
  "modifiedAt": "2021-02-23T05:56:41.123456Z",
  "finishedAt": null,
  "market": "BTC_USDT",
  "user": 12345,
  "type": "limit",
  "side": "buy",
  "amount": "0.01234000",
  "price": "35001",
  "takerFeeRate": "0",
  "makerFeeRate": "0",
  "isAmountAsQuote": false,
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

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
market | - | Name of the market

<aside class="notice">
The rate-limit for this endpoint is 10 req/min.
</aside>

## Get list of Orders

```python
import requests

requests.request(
  'GET',
  f'https://api.exbito.com/apiv2/orders?status=pending'
).json()
```

```shell
curl "https://api.exbito.com/apiv2/orders?status=pending"
```

```javascript
const axios = require('axios');

axios.get('https://api.exbito.com/apiv2/orders?status=pending')
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 193710506,
    "createdAt": "2021-02-23T05:56:41.123456Z",
    "modifiedAt": "2021-02-23T05:56:41.123456Z",
    "finishedAt": null,
    "market": "BTC_USDT",
    "user": 12345,
    "type": "limit",
    "side": "buy",
    "amount": "0.01234000",
    "price": "35001",
    "takerFeeRate": "0",
    "makerFeeRate": "0",
    "isAmountAsQuote": false,
    "loadStatus": "partiallyCancelled"
  }
]
```

This endpoint retrieves a list of orders.

### HTTP Request

`GET https://api.exbito.com/apiv2/orders`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
status | - | (Mandatory) `pending` or `finished`
marketName | - | Name of the market
offset | - | Offset
limit | - | Limit

<aside class="notice">
The rate-limit for this endpoint is 10 req/min.
</aside>
