#
- http (port 80)
- https (port 443)

#### Websocket
- ws 相當於 http, wss 相當於 https
- 與http最大不同為，websocket是持續雙向的連線，所以沒有重新連線或重新傳送header的過度負荷，連線數量只有一條雙向連線，反應更即時。
- 傳送的資料單位叫做Frame，目前RFC 6455中定義了幾種frame：text data、binary data、ping/pong、close等。

### Websocket Server 實作重點
- 建立handshake
- 接收資料
- 傳送資料

### Websocket API
- onopen
- onclose
- onerror
- onmessage
    - 當browser接收到server傳來的資料時會觸發。
