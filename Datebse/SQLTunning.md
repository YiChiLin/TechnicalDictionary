## SQL Tunning
- 避免負向查詢(not)，用if exist/if not exist，會造成較多的效能消耗
- function會造成index失效，大多的funciton是table scan 行為
- 不要對欄位做運算
- like '%林' 無法用index, 反之like '林%' 可以
- Where Name in (1,2,3) 能用到index 比 where XXX = OOO or XXX= ZZZ