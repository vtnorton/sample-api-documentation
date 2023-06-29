# Registro de Clientes

Use este endpoint para registrar um novo cliente.

## Requisição

### Requisição HTTP

```http
POST /customers
```

### cURL

```curl
curl --request POST --url 'https://api-url.com/customers' \
--header 'content-type: application/json' \
--data '{
   "name": "NOME DA PESSOA",
   "email": "email@empresa.com"
}'
```

```javascript
const url = "https://api-url.com/customers";
const data = {
  name: "NOME DA PESSOA",
  email: "email@empresa.com",
};

fetch(url, {
  method: "POST",
  headers: {
    "Content-Type": "application/json",
  },
  body: JSON.stringify({
    name: "NOME DA PESSOA",
    email: "email@empresa.com",
  }),
}).then((response) => {
  if (response.ok) {
    return response.json();
  } else {
    throw new Error("Erro: " + response.status);
  }
});
```

### Corpo da Requisição

| Parâmetro | Tipo     | Descrição                                                                                       |
| --------- | -------- | ----------------------------------------------------------------------------------------------- |
| `name`    | `string` | **Obrigatório.** Nome completo do cliente conforme consta no documento, sem abreviações.        |
| `email`   | `string` | Endereço de e-mail. O mesmo endereço de e-mail não pode ser usado por dois clientes diferentes. |

<details>
<summary>Corpo da requisição</summary>

```json
{
  "name": "NOME DA PESSOA",
  "email": "email@empresa.com"
}
```

</details>

## Resposta

O código de status 201 (Criado) indicará que a solicitação foi concluída com sucesso e a resposta trará os seguintes campos no formato JSON:

| Parâmetro | Tipo     | Descrição                                                                                                                    |
| --------- | -------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `id`      | `UUID`   | Código de identificação do cliente.                                                                                          |
| `name`    | `string` | Nome completo do cliente conforme consta no documento, sem abreviações.                                                      |
| `email`   | `string` | Endereço de e-mail. O mesmo endereço de e-mail não pode ser usado por dois clientes diferentes.                              |
| `status`  | `string` | O status da conta do cliente. O valor será `ativo` quando o cliente tiver associado uma conta bancária válida ao seu perfil. |

<details>
<summary>Corpo da resposta</summary>

```json
{
  "id": "a1b2c3d4",
  "name": "NOME DA PESSOA",
  "email": "email@empresa.com",
  "status": "ativo"
}
```

</details>

## Erro

A tabela a seguir fornece informações sobre erros comuns que podem ocorrer ao utilizar o padrão REST:

| Código de Erro | Descrição                                                                   |
| -------------- | --------------------------------------------------------------------------- |
| 400            | Solicitação Inválida - A solicitação é inválida ou não pode ser processada. |
| 401            | Não Autorizado - A solicitação requer autenticação do usuário.              |
| 403            | Proibido - O servidor entendeu a solicitação, mas recusa-se a autorizá-la.  |
| 500            | Erro Interno do Serv                                                        |

idor - Ocorreu um erro inesperado no lado do servidor. |

Consulte o código de erro específico e a descrição fornecidos na resposta para solucionar e resolver quaisquer problemas que possam ocorrer durante o processo de registro do cliente.
