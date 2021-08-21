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

## Other method
