# Introduction
The purpose of this documentation is to provide instructions on how to use the API to register a customer and, once a bank account is associated with the customer, to activate it.

## Customer Creation
To create a new customer using the API, you should follow these steps:

- Send a POST request to the [customer creation endpoint](./../reference/customer-register.md);
- Include the required fields, such as the customer's name and e-mail in the request body;
- Upon successfully creating a new customer, the API will respond with a status code indicating success, along with a unique customer ID that can be used to reference the customer in future API interactions.

## Bank Account Association
For the customer to be active it necessary to have a bank account associated with them. To do that using the API, you should follow these steps:

- Send a POST request to the [bank account association endpoint](./../reference/bank-account-association.md);
- Include the required fields for the bank account, such as the IBAN and holder's name, in the request body;
- Include any optional fields, such as the BIC number, if necessary;
- Upon successfully associating a bank account with the customer, the API will respond with a status code indicating success.

## Customer Activation
To activate a customer using the API, you should follow these steps:

- Send a POST request to the [customer activation endpoint](./../reference/customer-set-as-active.md) including the customer ID on the endpoint's path;
- It's important to notice that a bank account must be associated with the customer before they can be activated.
- Upon successfully activating the customer, the API will respond with a status code indicating success.

## Conclusion
By the end of this documentation, you will be able to use the API to register a new customer, associate a bank account with them, and activate the customer. Remember to consult the API reference for further details and any necessary authentication or authorization requirements.