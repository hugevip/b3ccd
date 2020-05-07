# Send a Transaction

## `sendtoaddress`:

```
./src/b3ccd -fallbackfee=0.0001
ADDR=$(./src/bsha-cli getnewaddress)
TXID=$(./src/b3cc-cli sendtoaddress $ADDR 49.999)
```

## `createrawtransaction`:

Use input(s), by txid and vout, to create spendable outputs at destination addr(s). Leftovers become fees collected by miners; be sure to account for change from your inputs. This example input spents most of a 50 B3CC coinbase reward.

```
./src/b3ccd
RAWTX=./src/b3cc-cli createrawtransaction "[{\"txid\":\"txid\",\"vout\":0}]" "{\"axxxxxxxxxxxx\":49.999}" 
SIGNEDRAWTX=./src/b3cc-cli signrawtransactionwithwallet $RAWTX
BROADCASTEDTXID=./src/b3cc-cli sendrawtransactionwithwallet $SIGNEDRAWTX
```
