---
description: Functions for WebSocket communication
---

# WebSocket

## Methods

### WebSocket_Connect
```lua
websocket_connect(url)
```
Connects to a WebSocket server at the specified URL.

Parameters:
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`url`: The WebSocket server URL

Returns: <kbd><mark style="color:brown;">**websocket**</mark></kbd> WebSocket connection object

### WebSocket_OnMessage
```lua
websocket_onmessage(websocket, callback)
```
Sets a callback function to handle incoming messages from the WebSocket.

Parameters:
* <kbd><mark style="color:brown;">**websocket**</mark></kbd>`websocket`: The WebSocket connection
* <kbd><mark style="color:pink;">**function**</mark></kbd>`callback`: Function to handle incoming messages
  * Callback receives: <kbd><mark style="color:yellow;">**string**</mark></kbd>`message`

Returns: <kbd><mark style="color:orange;">**void**</mark></kbd>

### WebSocket_Send
```lua
websocket_send(websocket, message)
```
Sends a string message to the connected WebSocket.

Parameters:
* <kbd><mark style="color:brown;">**websocket**</mark></kbd>`websocket`: The WebSocket connection
* <kbd><mark style="color:yellow;">**string**</mark></kbd>`message`: Message to send

Returns: <kbd><mark style="color:orange;">**void**</mark></kbd>

### WebSocket_Close
```lua
websocket_close(websocket)
```
Closes the connection with the WebSocket.

Parameters:
* <kbd><mark style="color:brown;">**websocket**</mark></kbd>`websocket`: The WebSocket connection to close

Returns: <kbd><mark style="color:orange;">**void**</mark></kbd>

See: [@examples/memory_manipulate](../examples/memory%20manipulate.md) for WebSocket usage examples. 