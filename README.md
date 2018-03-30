# Baconchain API Document

Simple API for Baconchain Wallet users to send and receive tokens payments.

## API List

### Create wallet

- Description：Generate a new wallet.
- Method：GET
- URL：`https://apibacon.com/create?key=$key`
    - `key`：API key.
- Response (success)：
    ``` 
    {
        "privatekey":"4075657654357a3dfd0db6c6c0521d0a3301df3aa09ff5a0770e37492bbc11bb449589b15f18fce62d0beadd763c4a54d1c41b08cb56e74971ad87b0d840539d3ad619349d7747c47a7cd43fc93208c3cefcd6fb87bf73d0066c947485ec0db2",
        "address":"XdyLpDEThUfCuB4kBSpTr7aeSUgWeh51XA"
    }

    ```
    - privatekey：Private key.
    - address：Baconchain address.
- Response (error)：
    ``` 
    {
        "message": "Argument missing."
    }
    ```
- Example
    ```
	https://apibacon.com/create?key=a2cdfea9-db4a-410a-b46c-92ccb318852b
	```

### Get balance

- Description：Balance inquiries and get tokens informations.
- Method：GET
- URL：`https://apibacon.com/balance?key=$key&address=$address`
    - `key`：API key.
    - `address`：Baconchain address.
- Response (success)：
    ```
    {
        [
            {
                "account":"Xuerapd489thr2BjKmcUAVcUycwsba5DPy",
                "token_id":"AKGkrkr16gq3Q5FnffXmz5gzjnHVguoheM",
                "balance":"3915",
                "name":"AppleCoin",
                "name_short":"APC",
                "icon_url":"https://img.com/e92fd1ef61bb8fb1a.png",
                "issue_price": "3",
                "current_price": "4"
            },
            {
                "account":"Xuerapd489thr2BjKmcUAVcUycwsba5DPy",
                "token_id":"mz5gzkr16gq6Q5FeffXwz5gzjnHVgYoheh",
                "balance":"578",
                "name":"GolfCoin",
                "name_short":"GFC",
                "icon_url":"https://img.com/th8fd1eas1bb8fb1a.png",
                "issue_price": "5",
                "current_price": "7"
            }
        ]
    }
    ```
    - account：Wallet address.
    - token_id：Token ID.
    - balance：Balance.
    - name：Name of token.
    - name_short：Short name of token.
    - icon_url：Icon path.
    - issue_price：Issueing price of token.
    - current_price：Current price of token.
- Response (error)：
    ``` 
    {
        "message": "Argument missing."
    }
    ```
- Example
    ```
	https://apibacon.com/balance?
	key=a2cdfea9-db4a-410a-b46c-92ccb318852b
	&
	address=sphrteQuR5qV4mwwRTEndR1z8TSy3K2W2P
	```

### Transaction

- Description：Tranfer tokens to other wallet.
- Method：GET
- URL：`https://apibacon.com/transaction?key=$key&privatekey=$privatekey&token_id=$token_id&to=$to&amount=$amount`
    - `key`：API key.
    - `privatekey`：Private key.
    - `token_id`：Token ID.
    - `to`：Recipient Baconchain address.
    - `amount`：Amount to send. Minimum unit: the 2nd decimal place.
- Response (success)：
    ```
    {
        "transaction_hash": "f322d01ad784e5deeb25464a5781c3b20971c1863679ca506e702e3e33c18e9c"
    }
    ```
    - transaction_hash：Transaction record.
- Response (error)：
    ``` 
    {
        "message": "Argument missing."
    }
    ```
- Example
	```
	https://apibacon.com/transaction?
	key=a2cdfea9-db4a-410a-b46c-92ccb318852b
	&
	privatekey=3f5cf166e9344f2e2d4bb2e251104f6650a4f83c019b411974e477ec16673db085d9c2bcdcbb14686bd97ce4aa713836de21b82df539efcfe5f56dd964cffb4752c9dc8d495e5a11b8a1af96f058ee6c8dd36c7c10e5293072b1287f9b9a6306
	&
	token_id=idgrsrfseuyrr6eew
	&
	to=s4y7jrSU9Fey4NNWGZtM6cpYcu7GoaQ8Ax
	&
	amount=15
	```

### ID address

- Description：Link address to email, phone number, credit card number or bank account.
- Method：GET
- URL：`https://apibacon.com/idaddress?key=$key&id=$id&address=$address`
    - `key`：API key.
    - `id`：Email / Phone number / Credit card number / Bank account
    - `address`：Baconchain address.
- Response (success)：
    ```
    {
        "transaction_hash": "5872d01ad784e5deeb25464a5781c3b20971c1863679ca506e702e3e33c18e9c"
    }
    ```
    - transaction_hash：Transaction hash
- Response (error)：
    ``` 
    {
        "message": "Argument missing."
    }
    ```
- Example
	```
	https://apibacon.com/idaddress?
	key=a2cdfea9-db4a-410a-b46c-92ccb318852b
	&
	id=amy1548@gmail.com
	&
	address=w8rs3hMX7jzHZEKmbfahNNqJAmLGkd38rb
	```