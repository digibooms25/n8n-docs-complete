# Venafi TLS Protect Datacenter node documentation

**Source:** https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.venafitlsprotectdatacenter/

---

# Venafi TLS Protect Datacenter node

Use the Venafi TLS Protect Datacenter node to automate work in Venafi TLS Protect Datacenter, and integrate Venafi TLS Protect Datacenter with other applications. n8n has built-in support for a wide range of Venafi TLS Protect Datacenter features, including creating, deleting, and getting certificates.

Credentials

Refer to [Venafi TLS Protect Datacenter credentials](../../credentials/venafitlsprotectdatacenter/) for guidance on setting up authentication.

## Operations

- Certificate
  - Create
  - Delete
  - Download
  - Get
  - Get Many
  - Renew
- Policy
  - Get

## Templates and examples

[Browse Venafi TLS Protect Datacenter integration templates](https://n8n.io/integrations/venafi-tls-protect-datacenter/), or [search all templates](https://n8n.io/workflows/)

## Related resources

n8n also provides:

- A [node](../n8n-nodes-base.venafitlsprotectcloud/) and [trigger](../../trigger-nodes/n8n-nodes-base.venafitlsprotectcloudtrigger/) node for Venafi TLS Protect Cloud.

## What to do if your operation isn't supported

If this node doesn't support the operation you want to do, you can use the [HTTP Request node](../../core-nodes/n8n-nodes-base.httprequest/) to call the service's API.

You can use the credential you created for this service in the HTTP Request node:

1. In the HTTP Request node, select **Authentication** > **Predefined Credential Type**.
2. Select the service you want to connect to.
3. Select your credential.

Refer to [Custom API operations](../../../custom-operations/) for more information.
