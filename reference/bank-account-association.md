# Bank Account Association
Use this endpoint to associate a customer to one bank account. This is mandatory to activate the customer.

### Prerequisite
To use this endpoint, it’s necessary that:
- there is one customer previously created to be associated with the bank account.

## Request
### HTTP Request
```http 
POST /bank_accounts
```

### cURL
```curl
curl --request POST --url 'https://api-url.com/bank_accounts' \ 
--header 'content-type: application/json'
--data '{
   "iban": "BR1800360305000010009795493C1",  
   "bic": "BKCOBRSPXXX",  
   "name": "NAME OF THE PERSON",  
   "customer_id": "11db9c8e-af85-4d35-9b2f-78a729548bd5"
}'
```

### Request Body
In the body, send the following fields in JSON format:

| Parameter | Type | Required? | Description |
| --- | --- | --- | --- |
| `iban` | `string` | Yes | The International Bank Account Number (IBAN) is a unique identifier assigned to each bank account. It consists of a country code, check digits, and a bank account number. The IBAN is used for international money transfers to ensure that funds are sent to the correct account. The IBAN must be in a valid format according to the country's regulations. |
| `bic` | `string` | No | The Bank Identifier Code (BIC), also known as SWIFT code, is a unique identification code for a particular bank. It consists of 8 or 11 characters and is used for international money transfers. The BIC must be in a valid format according to the bank's regulations. |
| `name` | `string` | Yes | The name of the account holder as it appears on official documents. This could be a person, business, or organization. It is important to ensure that the name provided matches the name on record with the bank to avoid issues with account verification or transactions. |
| `customer_id` | `string` | Yes | Customer identification code to associate with this bank account. |

## Response
The status code 201 (Created) will indicate that the request was completed successfully, the response will bring the following fields in JSON format:

| Parameter | Type | Description |
| --- | --- | --- |
| `iban` | `string` | The International Bank Account Number (IBAN) is a unique identifier assigned to each bank account. It consists of a country code, check digits, and a bank account number. The IBAN is used for international money transfers to ensure that funds are sent to the correct account. The IBAN must be in a valid format according to the country's regulations. |
| `bic` | `string` | The Bank Identifier Code (BIC), also known as SWIFT code, is a unique identification code for a particular bank. It consists of 8 or 11 characters and is used for international money transfers. The BIC must be in a valid format according to the bank's regulations. |
| `name` | `string` | The name of the account holder as it appears on official documents. This could be a person, business, or organization. It is important to ensure that the name provided matches the name on record with the bank to avoid issues with account verification or transactions. |
| `customer_id` | `string` | Customer identification code associateed with this bank account. |