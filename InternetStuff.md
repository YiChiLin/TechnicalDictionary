# Internet Kowledge
- http (port 80)
- https (port 443)

### Relationship between TCP/IP、Http、Socket
- [Reference Link](https://twgame.wordpress.com/2015/02/03/tcpiphttpsocketudp/)
![OSI Model](/OSIModel.png)

> **IP** is in Network layer.

> **TCP** is in Transport layer. It defines how data transport in internet.

> **Http** in Application layer. It defines how to pack data.
- Example: Web using Http as application protocol, encapsulate HTTP content and using TCP/IP to transfer data to the internet.

> **Socket** is an API for manipulating TCP/IP.

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
