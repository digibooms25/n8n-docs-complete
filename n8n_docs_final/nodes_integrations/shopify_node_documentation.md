# Shopify node documentation

**Source:** https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.shopify/

---

# Shopify node

Use the Shopify node to automate work in Shopify, and integrate Shopify with other applications. n8n has built-in support for a wide range of Shopify features, including creating, updating, deleting, and getting orders and products.

Credentials

Refer to [Shopify credentials](../../credentials/shopify/) for guidance on setting up authentication.

## Operations

- Order
  - Create an order
  - Delete an order
  - Get an order
  - Get all orders
  - Update an order
- Product
  - Create a product
  - Delete a product
  - Get a product
  - Get all products
  - Update a product

## Templates and examples

**Promote new Shopify products on Twitter and Telegram**

by Lorena

[View template details](https://n8n.io/workflows/1205-promote-new-shopify-products-on-twitter-and-telegram/)

**Run weekly inventories on Shopify sales**

by Lorena

[View template details](https://n8n.io/workflows/1207-run-weekly-inventories-on-shopify-sales/)

**Process Shopify new orders with Zoho CRM and Harvest**

by Lorena

[View template details](https://n8n.io/workflows/1206-process-shopify-new-orders-with-zoho-crm-and-harvest/)

[Browse Shopify integration templates](https://n8n.io/integrations/shopify/), or [search all templates](https://n8n.io/workflows/)

## What to do if your operation isn't supported

If this node doesn't support the operation you want to do, you can use the [HTTP Request node](../../core-nodes/n8n-nodes-base.httprequest/) to call the service's API.

You can use the credential you created for this service in the HTTP Request node:

1. In the HTTP Request node, select **Authentication** > **Predefined Credential Type**.
2. Select the service you want to connect to.
3. Select your credential.

Refer to [Custom API operations](../../../custom-operations/) for more information.
