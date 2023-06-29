# Associação de Conta Bancária

Use este endpoint para associar um cliente a uma conta bancária. Isso é obrigatório para ativar o cliente.

### Pré-requisito

Para usar este endpoint, é necessário que:

- já exista um cliente criado anteriormente para ser associado à conta bancária.

## Requisição

### Requisição HTTP

```http
POST /bank_accounts
```

### cURL

```curl
curl --request POST --url 'https://api-url.com/bank_accounts' \
--header 'content-type: application/json' \
--data '{
   "iban": "BR1800360305000010009795493C1",
   "bic": "BKCOBRSPXXX",
   "name": "NOME DA PESSOA",
   "customer_id": "11db9c8e-af85-4d35-9b2f-78a729548bd5"
}'
```

```javascript
const url = "https://api-url.com/bank_accounts";
const data = {
  iban: "BR1800360305000010009795493C1",
  bic: "BKCOBRSPXXX",
  name: "NOME DA PESSOA",
  customer_id: "11db9c8e-af85-4d35-9b2f-78a729548bd5",
};

fetch(url, {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify(data),
}).then((response) => {
  if (response.ok) {
    return response.json();
  } else {
    throw new Error("Erro: " + response.status);
  }
});
```

### Corpo da Requisição

No corpo da requisição, envie os seguintes campos no formato JSON:

| Parâmetro     | Tipo     | Descrição                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `iban`        | `string` | **Obrigatório.** O Número Internacional de Conta Bancária (IBAN) é um identificador único atribuído a cada conta bancária. Ele consiste em um código de país, dígitos de verificação e um número de conta bancária. O IBAN é usado para transferências internacionais de dinheiro para garantir que os fundos sejam enviados para a conta correta. O IBAN deve estar em um formato válido de acordo com as regulamentações do país. |
| `bic`         | `string` | O Código de Identificação do Banco (BIC), também conhecido como código SWIFT, é um código de identificação exclusivo para um banco específico. Ele consiste em 8 ou 11 caracteres e é usado para transferências internacionais de dinheiro. O BIC deve estar em um formato válido de acordo com as regulamentações do banco.                                                                                                        |
| `name`        | `string` | **Obrigatório.** O nome do titular da conta conforme consta em documentos oficiais. Isso pode ser uma pessoa, empresa ou organização. É importante garantir que o nome fornecido corresponda ao nome registrado no banco para evitar problemas com a verificação de conta ou transações.                                                                                                                                            |
| `customer_id` | `string` | **Obrigatório.** Código de identificação do cliente a ser associado a esta conta bancária.                                                                                                                                                                                                                                                                                                                                          |

<details>
<summary>Corpo da requisição</summary>

```json
{
  "iban": "BR180036

0305000010009795493C1",
  "bic": "BKCOBRSPXXX",
  "name": "NOME DA PESSOA",
  "customer_id": "11db9c8e-af85-4d35-9b2f-78a729548bd5"
}
```

</details>

## Resposta

O código de status 201 (Criado) indicará que a requisição foi concluída com sucesso e a resposta retornará os seguintes campos no formato JSON:

| Parâmetro     | Tipo     | Descrição                                                                                                                                                                                                                                                                                                                                                                                                          |
| ------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `iban`        | `string` | O Número Internacional de Conta Bancária (IBAN) é um identificador único atribuído a cada conta bancária. Ele consiste em um código de país, dígitos de verificação e um número de conta bancária. O IBAN é usado para transferências internacionais de dinheiro para garantir que os fundos sejam enviados para a conta correta. O IBAN deve estar em um formato válido de acordo com as regulamentações do país. |
| `bic`         | `string` | O Código de Identificação do Banco (BIC), também conhecido como código SWIFT, é um código de identificação exclusivo para um banco específico. Ele consiste em 8 ou 11 caracteres e é usado para transferências internacionais de dinheiro. O BIC deve estar em um formato válido de acordo com as regulamentações do banco.                                                                                       |
| `name`        | `string` | O nome do titular da conta conforme consta em documentos oficiais. Isso pode ser uma pessoa, empresa ou organização. É importante garantir que o nome fornecido corresponda ao nome registrado no banco para evitar problemas com a verificação de conta ou transações.                                                                                                                                            |
| `customer_id` | `string` | Código de identificação do cliente associado a esta conta bancária.                                                                                                                                                                                                                                                                                                                                                |

<details>
<summary>Corpo da resposta</summary>

```json
{
  "iban": "BR1800360305000010009795493C1",
  "bic": "BKCOBRSPXXX",
  "name": "NOME DA PESSOA",
  "customer_id": "11db9c8e-af85-4d35-9b2f-78a729548bd5"
}
```

</details>

## Erro

A tabela a seguir fornece informações sobre os erros comuns que podem ocorrer ao usar o padrão REST:

| Código de Erro | Descrição                                                                   |
| -------------- | --------------------------------------------------------------------------- |
| 400            | Solicitação Inválida - A solicitação é inválida ou não pode ser processada. |
| 401            | Não Autorizado - A solicitação requer autenticação do usuário.              |
| 403            | Proibido - O servidor entendeu a solicitação, mas se recusa a autorizá-la.  |
| 500            | Erro Interno do Servidor - Ocorreu um erro inesperado no lado do servidor.  |

Consulte o código de erro específico e a descrição fornecidos na resposta para solucionar e resolver quaisquer problemas que possam ocorrer durante o processo de associação da conta bancária.
