# Introdução

O objetivo desta documentação é fornecer instruções sobre como usar a API para registrar um cliente e, uma vez que uma conta bancária esteja associada ao cliente, ativá-la.

## Criação de Cliente

Para criar um novo cliente usando a API, você deve seguir estes passos:

- Envie uma solicitação POST para o [endpoint de criação de cliente](/referencia/pt-BR/cliente-registrar.md);
- Inclua os campos obrigatórios, como nome do cliente e e-mail, no corpo da solicitação;
- Após criar com sucesso um novo cliente, a API responderá com um código de status indicando o sucesso, juntamente com um ID de cliente exclusivo que pode ser usado para referenciar o cliente em interações futuras com a API.

## Associação de Conta Bancária

Para que o cliente esteja ativo, é necessário ter uma conta bancária associada a ele. Para fazer isso usando a API, você deve seguir estes passos:

- Envie uma solicitação POST para o [endpoint de associação de conta bancária](/referencia/pt-BR/associacao-conta-bancaria.md);
- Inclua os campos obrigatórios para a conta bancária, como o IBAN e o nome do titular, no corpo da solicitação;
- Inclua quaisquer campos opcionais, como o número BIC, se necessário;
- Ao associar com sucesso uma conta bancária ao cliente, a API responderá com um código de status indicando o sucesso.

## Ativação de Cliente

Para ativar um cliente usando a API, você deve seguir estes passos:

- Envie uma solicitação POST para o [endpoint de ativação de cliente](/referencia/pt-BR/cliente-ativar.md) incluindo o ID do cliente no caminho do endpoint;
- É importante observar que uma conta bancária deve estar associada ao cliente antes que ele possa ser ativado.
- Ao ativar com sucesso o cliente, a API responderá com um código de status indicando o sucesso.

## Conclusão

Ao final desta documentação, você será capaz de usar a API para registrar um novo cliente, associar uma conta bancária a ele e ativar o cliente. Lembre-se de consultar a referência da API para obter mais detalhes e quaisquer requisitos adicionais de autenticação ou autorização necessários.
