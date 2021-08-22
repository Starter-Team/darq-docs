#DARQ DOC

## Create Account method

Returns json data about new acoount and token.

### **URL**

/hedera/createAccount

### **Method**

`POST`

### **Data Params (body)**

| Name     | Description     | Type     |
| :------------- | :----------: | -----------: |
| masterAccountId  | The Hereda account of the presenter who is creating a new user account.   | String   |
| masterPrivateKey   | The Hereda private key of the presenter who is creating a new user account. | String  |
| mainnet   | Defines the environment in which to develop the transaction, whether it is a test (false)  or production (true) environment. | Boolean  |
| initialBalance   | The initial balance of the account, transferred from the operator account, in Hbar. | Number  |

> ⚠ When creating a new account an existing account will need to pay for the transaction fee to create the new account.

### **Response**
| Name       | Description     | Type     |
| :------------- | :----------: | -----------: |
| accountId | New account created by Hereda   | String    |
| publicKey   | New public key created by Hereda | String |
| privateKey   | New private key created by Hereda | String |


### Sample Request

```json
{ 
	"masterAccountId" : "0.0.000000", 
	"masterPrivateKey" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
	"mainnet": false,
	"initialBalance": 50
}
```

### **Success Response:**

**Status:** 200 **Content:**

```json
{ 
	"accountId" : "0.0.000000", 
	"publicKey" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
	"privateKey": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
}
```

### **Error Response:**

**Code:** 404 NOT FOUND **Content:**

```json
{ 
	"msg" : "Page not found"
}
```

**Code:** 500 SERVER ERROR **Content:** 

```json
{ 
	"msg" : "Environment variables masterAccountId and masterPrivateKey must be present"
}
```

## Transfer Token method

Returns json data about transfer a token.

### **URL**

/hedera/transferToken

### **Method**

`POST`

### **Data Params (body)**

| Name     | Description     | Type     |
| :------------- | :----------: | -----------: |
| senderAccountId  | The Hedera account of the presenter who is transfering  a token.   | String   |
| senderPrivateKey  | The Hedera private key of the presenter who is transfering  a token. | String  |
| receiverAccountId  | The Hedera account of the presenter who is receiving a token. | String  |
| tokenId  | The Id of the Token with which we are performing the operation. | String |
| amount  | Amount of token being transferred. | Number | 
| mainnet  | Defines the environment in which to develop the transaction, whether it is a test (false)  or production (true) environment. | Boolean  |


### **Response**
| Name       | Description     | Type     |
| :------------- | :----------: | -----------: |
| senderPreBalance  | The previous balance of the Hedera account of the presenter who is transferring a token.  | Number    |
| receiverPreBalance  | The previous balance of the Hedera private key of the presenter who is receiving a token. | Number |
| senderPostBalance  | The post balance in the Hedera account of the presenter who is transferring a token. | Number    |
| receiverPostBalance  | The post balance in the Hedera account of the presenter who is receiving a token. | Number |
| result  | Result of the operation carried out by inherit | String |


### Sample Request

```json
{ 
	"senderAccountId" : "0.0.000000", 
	"senderPrivateKey" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    	"receiverAccountId" : "0.0.000000", 
    	"tokenId" : "xxxxxxxxxx", 
    	"amount" : 0, 
	"mainnet": false
}
```
### **Success Response:**

**Status:** 200 **Content:**

```json
{ 
	"senderPreBalance" : 0, 
	"receiverPreBalance" : 0,
	"senderPostBalance" : 0, 
	"receiverPostBalance" : 0,
	"result": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
}
```

### **Error Response:**

**Code:** 404 NOT FOUND **Content:**

```json
{ 
	"msg" : "Page not found"
}
```

**Code:** 500 SERVER ERROR **Content:** 

```json
{ 
	"msg" : "Environment variables senderAccountId and senderPrivateKey must be present"
}
```


## Transfer TBAR method

Returns json data about transfer a Token BAR.

### **URL**

/hedera/transferTBAR

### **Method**

`POST`

### **Data Params (body)**

| Name     | Description     | Type     |
| :------------- | :----------: | -----------: |
| senderAccountId  | The Hedera account of the presenter who is transfering  a token BAR.   | String   |
| senderPrivateKey  | The Hedera private key of the presenter who is transfering  a token BAR. | String  |
| receiverAccountId  | The Hedera account of the presenter who is receiving a token BAR. | String  |
| amount  | Amount of token BAR being transferred. | Number | 
| mainnet  | Defines the environment in which to develop the transaction, whether it is a test (false)  or production (true) environment. | Boolean  |


### **Response**
| Name       | Description     | Type     |
| :------------- | :----------: | -----------: |
| senderPreBalance  | The previous balance of the Hedera account of the presenter who is transferring a token BAR.  | Number    |
| receiverPreBalance  | The previous balance of the Hedera private key of the presenter who is receiving a token BAR. | Number |
| senderPostBalance  | The post balance in the Hedera account of the presenter who is transferring a token BAR. | Number    |
| receiverPostBalance  | The post balance in the Hedera account of the presenter who is receiving a token BAR. | Number |
| result  | Result of the operation carried out by inherit | String |


### Sample Request

```json
{ 
	"senderAccountId" : "0.0.000000", 
	"senderPrivateKey" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    	"receiverAccountId" : "0.0.000000", 
    	"amount" : 0, 
	"mainnet": false
}
```
### **Success Response:**

**Status:** 200 **Content:**

```json
{ 
	"senderPreBalance" : 0, 
	"receiverPreBalance" : 0,
	"senderPostBalance" : 0, 
	"receiverPostBalance" : 0,
	"result": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
}
```

### **Error Response:**

**Code:** 404 NOT FOUND **Content:**

```json
{ 
	"msg" : "Page not found"
}
```

**Code:** 500 SERVER ERROR **Content:** 

```json
{ 
	"msg" : "Environment variables senderAccountId and senderPrivateKey must be present"
}
```

## Other Methods

## Submit Message method

Returns json data with a topicId and a receipt or a messageQuery
### **URL**

/hedera/createTopic

### **Method**

`POST`

### **Data Params (body)**

| Name     | Description     | Type     |
| :------------- | :----------: | -----------: |
| masterAccountId  | The Hereda account of the presenter who is creating a new user account.   | String   |
| masterPrivateKey   | The Hereda private key of the presenter who is creating a new user account. | String  |
| mainnet   | Defines the environment in which to develop the transaction, whether it is a test (false)  or production (true) environment. | Boolean  |
| message| Descriptive message to describe the operation | String|
| topicId (optional)| Unique identifier for a topic (used by the consensus service) | String|

> ⚠ If a topicId is not sent as a parameter then in the response you will receive it along with a receipt
### **Response (without a topicId)**
| Name       | Description     | Type     |
| :------------- | :----------: | -----------: |
| topicId| Unique identifier for a topic created by Hereda | String |
| receipt| The transaction receipt gives you information about a transaction in Hedera including whether or not the transaction reached consensus on the network   | JSON|


### **Response (with a topicId)**
| Name       | Description     | Type     |
| :------------- | :----------: | -----------: |
| topicId| Unique identifier for a topic created by Hereda | String |
| messageQuery| Object created by Hereda when submitting a transaction| String |

### Sample Request

```json
{ 
	"masterAccountId" : "0.0.000000", 
	"masterPrivateKey" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
	"mainnet": false
}
```

### **Success Response:**

**Status:** 200 **Content:**

```json
{ 
	"topicId" : "0.0.000000", 
	"receipt" : 
	{ 
		"status"= "SUCCESS", 
		"exchangeRate"=ExchangeRate{ 
				"hbars":1, 
				"cents":12, 
				"expirationTime":2100-01-01T00:00:00Z }, 
		"accountId":null, 
		"fileId":null, 
		"contractId":null, 
		"topicId":"0.0.000000", 
		"tokenId":null, 
		"topicSequenceNumber":null, 
		"topicRunningHash":null, 
		"totalSupply":0, 
		"scheduleId":0.0.2531 
	}
}
```

### **Error Response:**

**Code:** 404 NOT FOUND **Content:**

```json
{ 
	"msg" : "Page not found"
}
```

**Code:** 500 SERVER ERROR **Content:** 

```json
{ 
	"msg" : "Environment variables masterAccountId and masterPrivateKey must be present"
}
```

OR

**Code:** 500 SERVER ERROR **Content:** 

```json
{ 
	"msg" : "Environment variables myAccountId and myPrivateKey must be present"
}
```

