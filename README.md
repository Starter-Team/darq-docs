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
| masterAccountId  | The Hedera account of the presenter who is creating a new user account.   | String   |
| masterPrivateKey   | The Hedera private key of the presenter who is creating a new user account. | String  |
| mainnet   | Defines the environment in which to develop the transaction, whether it is a test (false)  or production (true) environment. | Boolean  |
| initialBalance   | The initial balance of the account, transferred from the operator account, in Hbar. | Number  |

> ⚠ When creating a new account an existing account will need to pay for the transaction fee to create the new account.

### **Response**
| Name       | Description     | Type     |
| :------------- | :----------: | -----------: |
| accountId | New account created by Hedera   | String    |
| publicKey   | New public key created by Hedera | String |
| privateKey   | New private key created by Hedera | String |


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


## Associate Account method

Returns json data about associate account.

### **URL**

/hedera/associateAccount

### **Method**

`POST`

### **Data Params (body)**

| Name     | Description     | Type     |
| :------------- | :----------: | -----------: |
| masterAccountId  | The Hedera account of the presenter who is creating a new user account.   | String   |
| masterPrivateKey   | The Hedera private key of the presenter who is creating a new user account. | String  |
| mainnet   | Defines the environment in which to develop the transaction, whether it is a test (false)  or production (true) environment. | Boolean  |
| tokenId   | The Id of the Token with which we are performing the operation. | String  |
| accountId   | The Hedera account of the presenter who wants to associate the account. | String  |
| accountPrivateKey   | The Hedera private key of the presenter who wants to associate the account | String  |

> ⚠ When creating a new account an existing account will need to pay for the transaction fee to create the new account.

### **Response**
| Name       | Description     | Type     |
| :------------- | :----------: | -----------: |
| result | Transaction result status    | String    |
| consensus   | Returns the receipt of a transaction | Object |


### Sample Request

```json
{ 
	"masterAccountId" : "0.0.000000", 
	"masterPrivateKey" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
	"mainnet": false,
	"tokenId": "0.0.0000000",
	"accountId" : "0.0.000000", 
	"accountPrivateKey" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
}
```

### **Success Response:**

**Status:** 200 **Content:**

```json
{ 
	"result" : "SUCCES", 
	"consensus" : {
	   "status": SUCCESS,
	   "exchangeRate": {
	     "hbars": 1,
	     "cents": 12, 
	     "expirationTime": 2100-01-01T00:00:00Z
	   }, 
	   "accountId": null,
	   "fileId": null, 
	   "contractId": null, 
	   "topicId": null, 
	   "tokenId": null, 
	   "topicSequenceNumber": null, 
	   "topicRunningHash": null, 
	   "totalSupply": 0, 
	   "scheduleId": 0.0.2531
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


## Create Token method

Returns json data about new token.

### **URL**

/hedera/createToken

### **Method**

`POST`

### **Data Params (body)**

| Name     | Description     | Type     |
| :------------- | :----------: | -----------: |
| masterAccountId  | The Hedera account of the presenter who is creating a new token.    | String    |
| masterPrivateKey   | The Hedera account of the presenter who is creating a new token.  | String    |
| ownerAccountId  | The Hedera account of the presenter who is creating a new token.   | String    |
| ownerPrivateKey   | The Hedera private key of the presenter who is creating a new token. | String    |
| mainnet   | Defines the environment in which to develop the transaction, whether it is a test (false)  or production (true) environment. | Boolean |
| tokenName   | The publicly visible name of the token. The token name is not unique. Maximum of 100 characters. | String    |
| tokenSymbol   | The publicly visible token symbol. The token symbol is not unique. Maximum of 100 characters. | String    |
| tokenSupply   | Specifies the initial supply of tokens to be put in circulation. | Number    |
| tokenDecimals   | The number of decimal places a token is divisible by | Number    |


### **Response**
| Name       | Description     | Type     |
| :------------- | :----------: | -----------: |
| tokenId | New token id created by Hedera   | String    |
| adminPublicKey   | New admin public key created by Hedera | String |
| adminPrivateKey   | New admin private key created by Hedera | String |
| treasuryPublicKey   | New treasury public key created by Hedera | String |
| treasuryPrivateKey   | New treasury private key created by Hedera | String |
| supplyPublicKey   | New supply public key created by Hedera | String |
| supplyPrivateKey   | New supply private key created by Hedera | String |
| freezePublicKey   | New freeze public key created by Hedera | String |
| freezePrivateKey   | New freeze private key created by Hedera | String |
| wipePublicKey   | New wipe public key created by Hedera | String |
| wipePrivateKey   | New wipe private key created by Hedera | String |


### Sample Request

```json
{ 
	"masterAccountId" : "0.0.0000000",
	"masterPrivateKey" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
	"ownerAccountId" : "0.0.0000000",
	"ownerPrivateKey" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
	"mainnet": false,
	"tokenName": "TokenNameCoin",
	"tokenSymbol": "TNC",
	"tokenSupply": 1000000,
	"tokenDecimals": 2,
}
```

### **Success Response:**

**Status:** 200 **Content:**

```json
{ 
	"tokenId" : "0.0.0000000", 
	"adminPublicKey" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
	"adminPrivateKey": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
	"treasuryPublicKey" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
	"treasuryPrivateKey": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
	"supplyPublicKey" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
	"supplyPrivateKey": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
	"freezePublicKey" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
	"freezePrivateKey": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
	"wipePublicKey" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
	"wipePrivateKey": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
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

## Account Info method

A query that returns the account balance for the specified account.

### **URL**

/hedera/accountInfo

### **Method**

`POST`

### **Data Params (body)**

| Name     | Description     | Type     |
| :------------- | :----------: | -----------: |
| masterAccountId  | The Hedera account of the user (Hedera credentials).   | String    |
| masterPrivateKey   | The Hedera private key of the user (Hedera credentials). | String    |
| accountId  | The account id of the user to be queried.   | String    |
| mainnet   | Defines the environment in which to develop the transaction, whether it is a test (false)  or production (true) environment. | Boolean |


### **Response**
| Name       | Description     | Type     |
| :------------- | :----------: | -----------: |
| hbar | The account balance for the specified account.   | String    |
| tokens   | The list of tokens assigned to this account. | Object |


### Sample Request

```json
{ 
	"masterAccountId" : "0.0.0000000",
	"masterPrivateKey" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
	"accountId" : "0.0.0000000",
	"mainnet": false,
}
```

### **Success Response:**

**Status:** 200 **Content:**

```json
{ 
	"hbar" : "50 ℏ",
	"tokens": {
		"0.0.390433": "100",
		"0.0.390437": "5000",
		"0.0.390438": "5000",
		"0.0.394589": "498820",
		"0.0.397095": "2000000",
		"0.0.460246": "19980",
		"0.0.460374": "500000",
		"0.0.478510": "99999785",
		"0.0.481115": "49999999980",
		"0.0.528921": "100000000",
		"0.0.532880": "10000000",
		"0.0.552732": "999999999759",
		"0.0.1569727": "100000",
		"0.0.1569728": "10000000",
		"0.0.1569729": "12390128321",
		"0.0.1569731": "12312312312",
		"0.0.1858435": "100000",
		"0.0.1858473": "1000000000",
		"0.0.1882329": "2313213"
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
| result  | Result of the operation carried out by Hedera | String |


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
| result  | Result of the operation carried out by Hedera | String |


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

## Create Topic method

Returns json data with a topicId and a receipt or a messageQuery
### **URL**

/hedera/createTopic

### **Method**

`POST`

### **Data Params (body)**

| Name     | Description     | Type     |
| :------------- | :----------: | -----------: |
| masterAccountId  | The Hedera account of the presenter who is creating a new user account.   | String   |
| masterPrivateKey   | The Hedera private key of the presenter who is creating a new user account. | String  |
| mainnet   | Defines the environment in which to develop the transaction, whether it is a test (false)  or production (true) environment. | Boolean  |
| message| Descriptive message to describe the operation | String|
| topicId (optional)| Unique identifier for a topic (used by the consensus service) | String|

> ⚠ If a topicId is not sent as a parameter then in the response you will receive it along with a receipt
### **Response (without a topicId)**
| Name       | Description     | Type     |
| :------------- | :----------: | -----------: |
| topicId| Unique identifier for a topic created by Hedera | String |
| receipt| The transaction receipt gives you information about a transaction in Hedera including whether or not the transaction reached consensus on the network   | JSON|


### **Response (with a topicId)**
| Name       | Description     | Type     |
| :------------- | :----------: | -----------: |
| topicId| Unique identifier for a topic created by Hedera| String |
| messageQuery| Object created by Hedera when submitting a transaction| JSON|

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
		"status": "SUCCESS", 
		"exchangeRate":{ 
				"hbars":1, 
				"cents":12, 
				"expirationTime":"2100-01-01T00:00:00Z" }, 
		"accountId":null, 
		"fileId":null, 
		"contractId":null, 
		"topicId":"0.0.000000", 
		"tokenId":null, 
		"topicSequenceNumber":null, 
		"topicRunningHash":null, 
		"totalSupply":0, 
		"scheduleId":"0.0.2531"
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


##  Get Topic Info method

Returns json data with a topicInfo and messages
### **URL**

/hedera/getTopicInfo

### **Method**

`POST`

### **Data Params (body)**

| Name     | Description     | Type     |
| :------------- | :----------: | -----------: |
| masterAccountId  | The Hedera account of the presenter who is creating a new user account.   | String   |
| masterPrivateKey   | The Hedera private key of the presenter who is creating a new user account. | String  |
| mainnet   | Defines the environment in which to develop the transaction, whether it is a test (false)  or production (true) environment. | Boolean  |
| topicId | Unique identifier for a topic (used by the consensus service) | String|


### **Response**
| Name       | Description     | Type     |
| :------------- | :----------: | -----------: |
| topicInfo| Returns the specific values for a topic | JSON|
| messages| Return the information of the messages of the topic with its contents   | JSON|


### Sample Request

```json
{ 
	"masterAccountId" : "0.0.000000", 
	"masterPrivateKey" : "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
	"mainnet": false,
	"topicId": "0.0.102736"
}
```

### **Success Response:**

**Status:** 200 **Content:**

```json
{ 
	"topicInfo" : 
	{ 
		"topicId": "0.0.102736", 
		"topicMemo":, 
		"runningHash":[ 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0. 0, 0,0,0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,0, 
		0, 0, 0, 0, 0, 0 ], 
		"sequenceNumber":0, 
		"expirationTime":"2021-02-09T03:17:07.258292001Z", 
		"adminKey":null, 
		"submitKey":null, 
		"autoRenewPeriod":"PT2160H", 
		"autoRenewAccountId":null
	},
	"messages":
	[
		{
			"message": 
			{
			    "operation": "create",
			    "did": "did:hedera:mainnet:7Prd74ry1Uct87nZqL3ny7aR7Cg46JamVbJgk8azVgUm;hedera:mainnet:fid=0.0.123",
			    "didDocumentBase64": "ewogICJAY29udGV...9tL3ZjLyIKICAgIH0KICBdCn0=",
			    "timestamp": "2020-04-23T14:37:43.511Z"
			},
			"contents": "Se creo un nuevo tema"
		}
	]
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

