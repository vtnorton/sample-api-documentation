# Customer Activation
Use this endpoint to activate the custumer's account.

### Prerequisite
To use this endpoint, it’s necessary that:

- the customer has a bank account associated with them.

## Request
### HTTP Request
```http 
POST /customers/{customer_id}/set_as_active/
```

### cURL
```curl
curl --request POST --url 'https://api-url.com/customers/{customer_id}/set_as_active/' 
```

### Path
In the path of this request send the following fields:
| Parameter | Description |
| --- | --- |
| `customer_id` | Customer identification code. |


## Response
The status code 200 (Ok) will indicate that the request was completed successfully, the response will bring the following fields in JSON format:

| Parameter | Type | Description |
| --- | --- | --- |
| `id` | `UUID` | Customer identification code. |
| `name` | `string` | Customer's full name as it appears on the document, without abbreviations. |
| `email` | `string` | E-mail address. The same e-mail address cannot be used by two customers. |
| `status` | `string` | The status of the customer's account. The value be `active` once the customer has associated a valid bank account with their profile. |
