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

```javascript
fetch("https://api-url.com/customers", {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    name: "NAME OF THE PERSON",
    email: "email@company.com",
  }),
}).then((response) => {
  if (response.ok) {
    return response.json();
  } else {
    throw new Error("Error: " + response.status);
  }
});
```

### Request Body

| Parameter | Type     | Description                                                                              |
| --------- | -------- | ---------------------------------------------------------------------------------------- |
| `name`    | `string` | **Required.** Customer's full name as it appears on the document, without abbreviations. |
| `email`   | `string` | E-mail address. The same e-mail address cannot be used by two customers.                 |

<details>
<summary>Request body</summary>

```json
{
  "name": "NAME OF THE PERSON",
  "email": "email@company.com"
}
```

</details>

## Response

The status code 201 (Created) will indicate that the request was completed successfully, the response will bring the following fields in JSON format:

| Parameter | Type     | Description                                                                                                                           |
| --------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| `id`      | `UUID`   | Customer identification code.                                                                                                         |
| `name`    | `string` | Customer's full name as it appears on the document, without abbreviations.                                                            |
| `email`   | `string` | Email address. The same e-mail address cannot be used by two customers.                                                               |
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
