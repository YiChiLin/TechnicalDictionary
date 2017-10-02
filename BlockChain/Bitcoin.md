---
title: Bitcoin
---
# Bitcoin
#### Main Net : Prefix 00 in decode address
#### Test Net : Prefix 6f in decode address

### Decode Address 
```c#
    byte[] byteArray = Encoders.Base58.DecodeData("15sYbVpRh6dyWycZMwPdxJWD4xbfxReeHe");
    string hex = Encoders.Hex.EncodeData(byteArray); //hexadecimal representation
```
### Create new keypair
- private key + puble key
```c#
    Key privateKey = new Key(); //Create private key
    BitcoinAddress address = privateKey.PubKey.GetAddress(Network.Main); //Get the public key, and derive the address on the Main network
```

