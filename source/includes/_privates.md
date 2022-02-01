# Private endpoints

## Get All Markets

```python
import requests

requests.request(
  'GET',
  f'https://api.exbito.com/apiv2/markets',
  headers={'X-Api-Key': MY_API_KEY, 'X-Api-Secret': MY_API_SECRET}
).json()
```

```shell
curl "https://api.exbito.com/apiv2/markets" \
  -H "X-Api-Key: $MY_API_KEY" \
  -H "X-Api-Secret: $MY_API_SECRET"
```

```javascript
const axios = require('axios');

axios.get('https://api.exbito.com/apiv2/markets', {
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
