# State Channels
- [Reference](https://www.cryptocompare.com/coins/guides/what-are-state-channels/)

### What is State Channels
- It's like a brige open between two users which can communicate with each other by transaction.
- It is off-chain and private, known only its participates. By sign its private key to ensure everything is authorized.

### Why State Channels?
- 為了減少手續費與減少node上大量儲存的資料。
- Currently each node in block chain have stored every deail of transaction which cost a lot of memory. 
- State channel can just update final outcome to blockchain as soon as channel is closed.
- It keep the information node store much smaller.
- It's advatage is instantt transaction with lower fee.
- P.S. however, smart contract might not suit for using state channel because smart contract might be used by multiple usrs in same time.
