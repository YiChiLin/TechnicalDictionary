# No SQL 
- Not Only SQL.
- 可水平擴充 (增加機器就能擴充資料庫存量)
- 打破Schema欄位的限制
- 資料遲早會一致 (CAP理論)
- 成熟度不足，版本升級風險高
- 最大的優點是能快速擴充

## DB 類型
### Key-Value DB
- 沒有像SQL一樣的Table Schema，取而代之的是Key-Value Pair的資料。每筆資料都是獨立的。
- Google的BigTable、Hadoop的HBase、Amazon的Dynamo、Cassandra、Hypertable、Redis、Memcached等都是這類Key-Value資料庫。

### In-memory DB
- 把資料放儲存在記憶體中，來提高讀取效率，大多使用在cache常用，加快網頁傳送速度，減少讀取硬碟的次數，不過系統此關機後就無法保存。類型DB包括了Memcached、Redis、Velocity、Tuple space等。
- Memcached、Redis也都是一種Key-Value資料架構的資料庫。

### Document-Oriented DB
- 主要用來儲存非結構性資料，像是HTML，沒有固定欄位，XML資料庫也是一種Document DB。常見的資料庫像是CouchDB、MongoDB以及Riak等。
- MongoDB可以在查詢指令中使用JavaScript。採取Master-Slave架構，1臺Master伺服器搭配多臺資料伺服器，資料伺服器間互相備援、容錯。

### Graph DB
- 關係越複雜的資料越適合使用圖學資料庫。
- 運用圖學架構來儲存節點間關係資料架構，例如用樹狀結構來組織從屬關係或網狀結構來儲存朋友關係，地理圖資系統通常也會用圖學資料庫來儲存地圖上每一點和鄰近點的關係，或用圖學資料庫來計算點與點之間最短的距離，也可以用同樣的概念來計算出人與人之間最短的交友距離。圖學資料庫最大的特性是對複雜性的擴充力。