# Help Scout node documentation

**Source:** https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.helpscout/

---

# Help Scout node

Use the Help Scout node to automate work in Help Scout, and integrate Help Scout with other applications. n8n has built-in support for a wide range of Help Scout features, including creating, updating, deleting, and getting conversations, and customers.

Credentials

Refer to [Help Scout credentials](../../credentials/helpscout/) for guidance on setting up authentication.

## Operations

- Conversation
  - Create a new conversation
  - Delete a conversation
  - Get a conversation
  - Get all conversations
- Customer
  - Create a new customer
  - Get a customer
  - Get all customers
  - Get customer property definitions
  - Update a customer
- Mailbox
  - Get data of a mailbox
  - Get all mailboxes
- Thread
  - Create a new chat thread
  - Get all chat threads

## Templates and examples

[Browse Help Scout integration templates](https://n8n.io/integrations/helpscout/), or [search all templates](https://n8n.io/workflows/)

## What to do if your operation isn't supported

If this node doesn't support the operation you want to do, you can use the [HTTP Request node](../../core-nodes/n8n-nodes-base.httprequest/) to call the service's API.

You can use the credential you created for this service in the HTTP Request node:

1. In the HTTP Request node, select **Authentication** > **Predefined Credential Type**.
2. Select the service you want to connect to.
3. Select your credential.

Refer to [Custom API operations](../../../custom-operations/) for more information.
