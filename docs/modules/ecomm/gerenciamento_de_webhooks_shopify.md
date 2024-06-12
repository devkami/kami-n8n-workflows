# Gestão de Webhooks do Shopify [PT](gerenciamento_de_webhooks_shopify.md) | [EN](gerenciamento_de_webhooks_shopify-en_us.md)

Este documento descreve como importar e usar o fluxo de trabalho [Shopify Webhooks Management](../../../modules/ecomm/gerenciamento_de_webhooks_shopify.json) no N8N para gerenciar webhooks para uma loja Shopify.

## Importando e usando o fluxo de trabalho no N8N

### Importando o fluxo de trabalho

1. **Importar** [gerenciamento_webhooks_shopify.json](../../../modules/ecomm/gerenciamento_webhooks_shopify.json) arquivo armazenado na pasta `modules/ecomm/` neste projeto conforme mencionado em [Gerenciamento Básico de Fluxo de Trabalho Operations](../../../README.md#basic-workflow-management-operations) neste README do projeto.
2. **Nomeie** o fluxo de trabalho como preferir.
3. **Salve** e o fluxo de trabalho aparecerá na sua lista de fluxos de trabalho.

![Nome do fluxo de trabalho importado](../../assets/pictures/ecomm/pic_01_n8n_name_workflow.png)
*Legenda: Nome do fluxo de trabalho importado.*

![Salvar fluxo de trabalho importado](../../assets/pictures/ecomm/pic_02_n8n_save_workflow.png)
*Legenda: Salvar fluxo de trabalho importado.*

### Configurando variáveis ​​de ambiente

1. **Atualize** as credenciais da API do Shopify editando o nó `env-vars` conforme mencionado em [Operações básicas de gerenciamento de fluxo de trabalho](../../../README.md#basic-workflow-management- operações) neste projeto README.

 ```javascript
 const env_vars = {
 "shop_url": "https://sua_loja_shopify.myshopify.com",
 "test_url": "https://your_test_shopify_store.myshopify.com",
 };
 ```

2. **Salve as alterações.**

### Pesquisando Webhooks

1. **Configure** o nó `Get Webhooks` com as seguintes configurações:

- **Autenticação:** Tipo de credencial predefinida
- **Tipo de credencial de nó:** API de token de acesso do Shopify
- **URL:** `={{ $json.shop_url }}/admin/api/2024-04/webhooks.json`

2. **Salve** a configuração do nó.

### Inserindo um Webhook

1. **Configure** o nó `webhook-data` para preparar os dados do webhook a serem inseridos:

 ```javascript
 const webhookData = {
 "endereço": "https://sua_shopify_store.myshopify.com/webhook/endpoint",
 "tópico": "checkout/atualização",
 "formato": "json"
 };
 retornar {json: webhookData};
 ```

2. **Configure** o nó `Post Webhook` com as seguintes configurações:

- **Autenticação:** Tipo de credencial predefinida
- **Tipo de credencial de nó:** API de token de acesso do Shopify
- **Método de solicitação:** POST
- **URL:** `={{ $json.shop_url }}/admin/api/2024-04/webhooks.json`
- **Parâmetros do corpo:** Use a saída do nó `webhook-data`.

3. **Salve** a configuração do nó.

### Excluindo um webhook

1. **Configure** o nó `webhook-id` para fornecer o ID do webhook a ser excluído:

 ```javascript
 const webhookID = "seu_webhook_id_to_delete";
 retornar { json: {webhookID: webhookID} };
 ```

2. **Configure** o nó `Delete Webhook` com as seguintes configurações:

- **Autenticação:** Tipo de credencial predefinida
- **Tipo de credencial de nó:** API de token de acesso do Shopify
- **Método de solicitação:** DELETE
- **URL:** `={{ $('env-vars').first().json.shop_url }}/admin/api/2024-04/webhooks/{{ $('webhook-id') .first().json.webhookID }}.json`

1. **Salve** a configuração do nó.

### Referências de documentação da API

- [Documentação sobre Webhook da API Shopify](https://shopify.dev/docs/api/admin-rest/2024-04/resources/webhook)
- [Webhook Shopify Apps](https://shopify.dev/docs/apps/build/webhooks)
