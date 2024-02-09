# Krist API
The CarrotPay Krist API is the way to add to the database  
Some endpoints may cost Krist, others won't  
To use this, pay `carrotpay.kst` the cost and transaction metadata specified  
Examples are using syntax for the [CarrotPay](https://pinestore.cc/projects/44/carrotpay) ComputerCraft program  

### Get a name
Cost: 10 krist  
This endpoint will let you buy a name  
`get_name=<name>`  
example:
```
^pay carrotpay.kst 10 get_name=example.crt
```
This endpoint cannot be used with a SwitchCraft ingame wallet, your own wallet is required  
Returns nothing on success

### Pay to a name
Cost: Any  
This endpoint lets you pay to a .crt name with programs that don't support .crt names  
`to=<name>`  
example:  
```
^pay carrotpay.kst 16 to=example.crt
```
If you are using the CarrotPay ComputerCraft program, you do not need to use this endpoint as it has .crt names supported natively.
Returns nothing on success.

### Transfer a name to another address
Cost: 0  
This endpoint lets you transfer one of your names to a new address  
`name=<name>;transfer_to=<new_address>`  
example:  
```
^pay carrotpay.kst 1 name=example.crt;transfer_to=katze60dfn
```
At least 1 krist is required to activate this endpoint due to limitations with Krist  
Returns a refund with message `Successfully transferred <name> to <new_address>`


