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

## Request

It's not necessary to send one body in the request.

## Response

The status code 200 (Ok) will indicate that the request was completed successfully, the response will bring the following fields in JSON format:

| Parameter | Type     | Description                                                                                                                           |
| --------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `id`      | `UUID`   | Customer identification code.                                                                                                         |
| `name`    | `string` | Customer's full name as it appears on the document, without abbreviations.                                                            |
| `email`   | `string` | E-mail address. The same e-mail address cannot be used by two customers.                                                              |
| `status`  | `string` | The status of the customer's account. The value be `active` once the customer has associated a valid bank account with their profile. |

<details>
<summary>Response body</summary>

```json
{
  "id": "a1b2c3d4",
  "name": "NAME OF THE PERSON",
  "email": "email@company.com",
  "status": "active"
}
```

</details>

## Error

The following table provides information about common errors that can occur when using the REST standard:

| Error Code | Description                                                                |
| ---------- | -------------------------------------------------------------------------- |
| 400        | Bad Request - The request is invalid or cannot be processed.               |
| 401        | Unauthorized - The request requires user authentication.                   |
| 403        | Forbidden - The server understood the request but refuses to authorize it. |
| 500        | Internal Server Error - An unexpected error occurred on the server side.   |

Please refer to the specific error code and description provided in the response to troubleshoot and resolve any issues you may encounter during the customer registration process.
