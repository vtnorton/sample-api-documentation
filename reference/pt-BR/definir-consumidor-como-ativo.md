# Ativação de Cliente

Use este endpoint para ativar a conta do cliente.

### Pré-requisito

Para usar este endpoint, é necessário que:

- o cliente tenha uma conta bancária associada a ele.

## Requisição

### Requisição HTTP

```http
POST /customers/{customer_id}/set_as_active/
```

### cURL

```curl
curl --request POST --url 'https://api-url.com/customers/{customer_id}/set_as_active/'
```

### Caminho

No caminho desta requisição, envie os seguintes campos:
| Parâmetro | Descrição |
| --- | --- |
| `customer_id` | Código de identificação do cliente. |

## Requisição

Não é necessário enviar um corpo na requisição.

## Resposta

O código de status 200 (Ok) indicará que a requisição foi concluída com sucesso, e a resposta retornará os seguintes campos no formato JSON:

| Parâmetro | Tipo     | Descrição                                                                                                                     |
| --------- | -------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `id`      | `UUID`   | Código de identificação do cliente.                                                                                           |
| `name`    | `string` | Nome completo do cliente conforme consta no documento, sem abreviações.                                                       |
| `email`   | `string` | Endereço de e-mail. O mesmo endereço de e-mail não pode ser usado por dois clientes.                                          |
| `status`  | `string` | O status da conta do cliente. O valor será `active` quando o cliente tiver associado uma conta bancária válida ao seu perfil. |

<details>
<summary>Corpo da resposta</summary>

```json
{
  "id": "a1b2c3d4",
  "name": "NOME DA PESSOA",
  "email": "email@company.com",
  "status": "active"
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

Consulte o código de erro específico e a descrição fornecidos na resposta para solucionar e resolver quaisquer problemas que possam ocorrer durante o processo de ativação da conta do cliente.
