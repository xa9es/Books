---
description: Functions for making HTTP requests
---

## Methods

### HttpGet
```lua
httpget(url)
```
Performs an HTTP GET request and returns the response content.

Parameters:
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`url`: The target URL for the request

Returns: <kbd><mark style="color:yellow;">**string**</mark></kbd> Response content

### HttpPost
```lua
httppost(url, data, content_type, accept[cookie, referer, origin])
```
Performs an HTTP POST request and returns the response content.

Parameters:
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`url`: The target URL for the request
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`data`: The data to send in the request body
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`content_type`: The Content-Type header value
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`accept`: The Accept header value
* <kbd><mark style="color:purple;">**OPTIONAL**</mark></kbd> <kbd><mark style="color:yellow;">**string**</mark></kbd>`cookie`: The Cookie header value
* <kbd><mark style="color:purple;">**OPTIONAL**</mark></kbd> <kbd><mark style="color:yellow;">**string**</mark></kbd>`referer`: The Referer header value
* <kbd><mark style="color:purple;">**OPTIONAL**</mark></kbd> <kbd><mark style="color:yellow;">**string**</mark></kbd>`origin`: The Origin header value

Returns: <kbd><mark style="color:yellow;">**string**</mark></kbd> Response content