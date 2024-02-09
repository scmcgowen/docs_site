# HTTP API

The CarrotPay HTTP API is the way to read data from the CarrotPay database.
The API is on `carrotpay.herrkatze.com`

### Get names from an Address

`GET /names?address=<address>`
This will return a JSON list of addresses owned by that address
example:
```
/names?address=katze60dfn
["katze.crt", "katzetest.crt"]
```

### Get the address from a name

`GET /address?name=<name>`
This will get the address a name is owned by
example:
```
/address?name=katze.crt
katze60dfn
```
