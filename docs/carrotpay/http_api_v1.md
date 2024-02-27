# HTTP API V1 (Deprecated)

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

### Get the full data from a name

`GET /name_data?name=<name>`
This will get the full name data of a name.  
Compatible with the Krist name endpoint
example:
```
/name_data?name=katze.crt
{
"ok":true,
"name":{
    "name": "katze.crt",
    "owner": "katze60dfn",
    "original_owner": "katze60dfn",
    "registered": "2024-02-13T05:23:28",
    "updated": "2024-02-13T05:23:28"
    }
}
```
