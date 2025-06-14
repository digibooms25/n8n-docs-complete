# Stripe node documentation

**Source:** https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.stripe/

---

# Stripe node

Use the Stripe node to automate work in Stripe, and integrate Stripe with other applications. n8n has built-in support for a wide range of Stripe features, including getting balance, creating charge, and deleting customers.

Credentials

Refer to [Stripe credentials](../../credentials/stripe/) for guidance on setting up authentication.

## Operations

- Balance
  - Get a balance
- Charge
  - Create a charge
  - Get a charge
  - Get all charges
  - Update a charge
- Coupon
  - Create a coupon
  - Get all coupons
- Customer
  - Create a customer
  - Delete a customer
  - Get a customer
  - Get all customers
  - Update a customer
- Customer Card
  - Add a customer card
  - Get a customer card
  - Remove a customer card
- Source
  - Create a source
  - Delete a source
  - Get a source
- Token
  - Create a token

## Templates and examples

**Update HubSpot when a new invoice is registered in Stripe**

by Jonathan

[View template details](https://n8n.io/workflows/1468-update-hubspot-when-a-new-invoice-is-registered-in-stripe/)

**Simplest way to create a Stripe Payment Link**

by Emmanuel Bernard

[View template details](https://n8n.io/workflows/2195-simplest-way-to-create-a-stripe-payment-link/)

**Streamline Your Zoom Meetings with Secure, Automated Stripe Payments**

by Emmanuel Bernard

[View template details](https://n8n.io/workflows/2192-streamline-your-zoom-meetings-with-secure-automated-stripe-payments/)

[Browse Stripe integration templates](https://n8n.io/integrations/stripe/), or [search all templates](https://n8n.io/workflows/)

## What to do if your operation isn't supported

If this node doesn't support the operation you want to do, you can use the [HTTP Request node](../../core-nodes/n8n-nodes-base.httprequest/) to call the service's API.

You can use the credential you created for this service in the HTTP Request node:

1. In the HTTP Request node, select **Authentication** > **Predefined Credential Type**.
2. Select the service you want to connect to.
3. Select your credential.

Refer to [Custom API operations](../../../custom-operations/) for more information.
