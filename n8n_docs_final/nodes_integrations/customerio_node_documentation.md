# Customer.io node documentation

**Source:** https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.customerio/

---

# Customer.io node

Use the Customer.io node to automate work in Customer.io, and integrate Customer.io with other applications. n8n has built-in support for a wide range of Customer.io features, including creating and updating customers, tracking events, and getting campaigns.

Credentials

Refer to [Customer.io credentials](../../credentials/customerio/) for guidance on setting up authentication.

## Operations

- Customer
  - Create/Update a customer.
  - Delete a customer.
- Event
  - Track a customer event.
  - Track an anonymous event.
- Campaign
  - Get
  - Get All
  - Get Metrics
- Segment
  - Add Customer
  - Remove Customer

## Templates and examples

[Browse Customer.io integration templates](https://n8n.io/integrations/customerio/), or [search all templates](https://n8n.io/workflows/)

## What to do if your operation isn't supported

If this node doesn't support the operation you want to do, you can use the [HTTP Request node](../../core-nodes/n8n-nodes-base.httprequest/) to call the service's API.

You can use the credential you created for this service in the HTTP Request node:

1. In the HTTP Request node, select **Authentication** > **Predefined Credential Type**.
2. Select the service you want to connect to.
3. Select your credential.

Refer to [Custom API operations](../../../custom-operations/) for more information.
