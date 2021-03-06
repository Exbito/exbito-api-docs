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

## Get list of Balances

```python
import requests

requests.request(
  'GET',
  f'https://api.exbito.com/apiv2/balances
).json()
```

```shell
curl "https://api.exbito.com/apiv2/balances"
```

```javascript
const axios = require('axios');

axios.get('https://api.exbito.com/apiv2/balances')
```

> The above command returns JSON structured like this:

```json
[
  {
    "name": "ETH",
    "available": "9138",
    "freeze": "0"
  },
  {
    "name": "BTC",
    "available": "101",
    "freeze": "10"
  }
]
```

This endpoint retrieves a list of balances.

### HTTP Request

`GET https://api.exbito.com/apiv2/balances`

<aside class="notice">
The rate-limit for this endpoint is 10 req/min.
</aside>

## Show cryptocurrency deposit info

```python
import requests

url = "https://api.exbito.com/apiv2/deposits?cryptocurrencySymbol=BTC&chain=btc"

payload={}
files={}
headers = {}

response = requests.request("SHOW", url, headers=headers, data=payload, files=files)

print(response.text)
```

```shell
curl --location --request SHOW 'https://api.exbito.com/apiv2/deposits?cryptocurrencySymbol=BTC&chain=btc'
```

```javascript
var axios = require('axios');
var FormData = require('form-data');
var data = new FormData();

var config = {
  method: 'show',
  url: 'https://api.exbito.com/apiv2/deposits?cryptocurrencySymbol=BTC&chain=btc',
  headers: { 
    ...data.getHeaders()
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "user": "1",
  "extra": null,
  "creation": "2019-03-19T12:11:10.337+03:00",
  "expiration": null,
  "address": "1D6CqUvHtQRXU4TZrrj5j1iofo8f4oXyLj",
  "tag": null
}
```

This endpoint retrieves info of a currency.

### HTTP Request

`SHOW https://api.exbito.com/apiv2/deposits`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
cryptocurrencySymbol | - | (Mandatory)
chain | - | (Mandatory) Chain of cryptocurrency

<aside class="notice">
The rate-limit for this endpoint is 10 req/min.
</aside>

## Renew cryptocurrency deposit info

```python
import requests

url = "https://api.exbito.com/apiv2/deposits?cryptocurrencySymbol=BTC&chain=btc"

payload={}
files={}
headers = {}

response = requests.request("RENEW", url, headers=headers, data=payload, files=files)

print(response.text)

```

```shell
curl --location --request RENEW 'https://api.exbito.com/apiv2/deposits?cryptocurrencySymbol=BTC&chain=btc'
```

```javascript
var axios = require('axios');
var FormData = require('form-data');
var data = new FormData();

var config = {
  method: 'renew',
  url: 'https://api.exbito.com/apiv2/deposits?cryptocurrencySymbol=BTC&chain=btc',
  headers: { 
    ...data.getHeaders()
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "user": "1",
  "extra": null,
  "creation": "2019-03-19T12:11:10.337+03:00",
  "expiration": null,
  "address": "1D6CqUvHtQRXU4TZrrj5j1iofo8f4oXyLj",
  "tag": null
}
```

This endpoint renew deposit info.

### HTTP Request

`RENEW https://api.exbito.com/apiv2/deposits`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
cryptocurrencySymbol | - | (Mandatory)
chain | - | (Mandatory) Chain of cryptocurrency

<aside class="notice">
The rate-limit for this endpoint is 10 req/min.
</aside>
