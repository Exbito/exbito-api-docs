# Errors

All non-successful responses have status code between 400-499. For the API with more than one error code, you can
read `X-Reason` header on the response to find out more info about the error.

<aside class="notice">
The `X-Reason` headers might not be available on some errors. But in most cases, keeping an eye on `X-Reason` header will help you finding the error reason.
</aside>

The Exbito API uses the following error codes:

Error Code | X-Reason | Meaning
---------- | ---------- | -------
400 | - | Bad Request -- Your request is invalid.
401 | - | Unauthorized -- Your API key is wrong.
403 | - | Forbidden -- The requested resource is accessible for you.
404 | - | Not Found -- The specified resource could not be found.
400 | amount-not-in-range | The provided amount is not acceptable. You can find the min and max of the amount values form the `/markets` endpoint.
400 | quote-not-in-range | The provided quote is not acceptable. You can find the min and max of the quote values form the `/markets` endpoint.
400 | bad-amount-step | The provided amount must be divisible by `amountStep`. You can find the step of the amount values form the `/markets` endpoint.
429 | - | Too Many Requests -- You're requesting too many times! Slow down!
500 | - | Internal Server Error -- We had a problem with our server. Try again later.
503 | - | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
