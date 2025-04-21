# Network

# Methods

## WebSocket_Connect
```lua
websocket_connect(url)
```
Connects to a WebSocket server at the specified URL

## WebSocket_OnMessage
```lua
websocket_onmessage(websocket, callback)
```
Sets a callback function to handle incoming messages from the WebSocket 

## WebSocket_Send
```lua
websocket_send(websocket, message)
```
Sends a string message to the connected WebSocket

## WebSocket_Close
```lua
websocket_close(websocket)
```
Closes the connection with the WebSocket

# Examples

## WebSocket Example
```lua
-- Connect to a WebSocket server
local ws = websocket_connect("ws://severe-websocket-test.glitch.me")

-- Set up a message handler
websocket_onmessage(ws, function(msg)
    warn(msg)
end)

-- Send a message
websocket_send(ws, "Hello World!")

-- Wait for 1 second
wait(1)

-- Close the connection
websocket_close(ws)
``` 