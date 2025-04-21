## HttpGet
```lua
httpget(url)
```
Performs an HTTP GET request and returns the response content `string`

## HttpPost
```lua
httppost(url, data, content_type, accept[cookie, referer, origin])
```
Performs an HTTP POST request and returns the response content `string`

Parameters:
- `url`: The target URL for the request
- `data`: The data to send in the request body
- `content_type`: The Content-Type header value
- `accept`: The Accept header value
- `cookie` (optional): The Cookie header value
- `referer` (optional): The Referer header value
- `origin` (optional): The Origin header value