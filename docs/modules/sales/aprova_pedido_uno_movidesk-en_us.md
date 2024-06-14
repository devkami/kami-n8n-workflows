# Order Approval UNO Movidesk Workflow [PT](aprova_pedido_uno_movidesk.md) | [EN](aprova_pedido_uno_movidesk-en_us.md)

The Order Approval workflow integrates the ERP UNO with the Movidesk service desk management system to automate order approval processes. This document describes how to import and use the workflow [Order Approval UNO Movidesk](../../../modules/sales/aprova_pedido_uno_movidesk.json) in N8N.

## Importing and Using the Workflow in N8N

### Importing the Workflow

1. **Import** [aprova_pedido_uno_movidesk.json](../../../modules/sales/aprova_pedido_uno_movidesk.json) file stored in the `modules/sales/` folder in this project as mentioned in [Basic Workflow Management Operations](../../../README.md#basic-workflow-management-operations) section on this project README.
2. **Name** the workflow as you prefer.
3. **Save** it and then the workflow will appear in your list of workflows.

![Name Imported Workflow](../../assets/pictures/sales/pic_01_n8n_name_workflow.png)
*Caption: Name Imported Workflow.*

![Save Imported Workflow](../../assets/pictures/sales/pic_02_n8n_save_workflow.png)
*Caption: Save Imported Workflow.*

### Setting Up Environment Variables

1. **Update** the API credentials for UNO and Movidesk by editing the `env-vars` node as mentioned in [Basic Workflow Management Operations](../../../README.md#basic-workflow-management-operations) section on this project README.

    ```javascript
    const apis_credentials = {
      "uno": {
        "url": "http://api.unoerp.com.br/v1",
        "account_id": "your_uno_account_id",
        "secret_key": "your_uno_secret_key",
      },
      "movidesk": {
        "url": "https://api.movidesk.com/public/v1",
        "token": "your_movidesk_token",
      },
    };
    ```

2. **Save the changes.**

### Testing the Workflow

1. Navigate to the workflow settings and **trigger** the `test workflow` button.

    ![Test Mode](../../assets/pictures/sales/pic_03_n8n_test_workflow.png)
    *Caption: Manually triggering the workflow for testing.*

2. Check the **execution logs** to verify the workflow's behavior as mentioned in [Basic Workflow Management Operations](../../../README.md#basic-workflow-management-operations) section on this project README.

### Activating the Workflow

After successful testing, switch the workflow to 'Active' mode as mentioned in [Basic Workflow Management Operations](../../../README.md#basic-workflow-management-operations) section on this project README.

### API Documentation References

- [ERP UNO API Documentation](https://unoerp.com.br/)
- [Movidesk API Documentation for Tickets](https://support.movidesk.com/kb/pt-br/article/161485/tickets-api)
