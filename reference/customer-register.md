# Customer Registration
Use this endpoint to register a new customer.

### Prerequisite
To use this endpoint, it’s necessary that:

- the customer has a bank account associated with it.

## Request
### HTTP Request
```http 
POST /customers
```
### cURL
```curl
curl --request POST --url 'https://api-url.com/customers' \ 
--header 'content-type: application/json'
--data '{
   "name": "NAME OF THE PERSON",  
   "email": "email@company.com"
}'
```


### Request Body
| Parameter | Type | Description |
| --- | --- | --- |
| `name` | `string` | **Required.** Customer's full name as it appears on the document, without abbreviations. |
| `email` | `string` | E-mail address. The same e-mail address cannot be used by two customers. |

## Response
The status code 201 (Created) will indicate that the request was completed successfully, the response will bring the following fields in JSON format:

| Parameter | Type | Description |
| --- | --- | --- |
| `id` | `UUID` | Customer identification code. |
| `name` | `string` | Customer's full name as it appears on the document, without abbreviations. |
| `email` | `string` | Email address. The same e-mail address cannot be used by two customers. |
| `status` | `string` | The status of the customer's account. The value be `active` once the customer has associated a valid bank account with their profile. |

