# Venafi TLS Protect Cloud node documentation

**Source:** https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.venafitlsprotectcloud/

---

# Venafi TLS Protect Cloud node

Use the Venafi TLS Protect Cloud node to automate work in Venafi TLS Protect Cloud, and integrate Venafi TLS Protect Cloud with other applications. n8n has built-in support for a wide range of Venafi TLS Protect Cloud features, including deleting and downloading certificates, as well as creating certificates requests.

Credentials

Refer to [Venafi TLS Protect Cloud credentials](../../credentials/venafitlsprotectcloud/) for guidance on setting up authentication.

## Operations

- Certificate
  - Delete
  - Download
  - Get
  - Get Many
  - Renew
- Certificate Request
  - Create
  - Get
  - Get Many

## Templates and examples

[Browse Venafi TLS Protect Cloud integration templates](https://n8n.io/integrations/venafi-tls-protect-cloud/), or [search all templates](https://n8n.io/workflows/)

## Related resources

Refer to [Venafi's REST API documentation](https://docs.venafi.cloud/api/vaas-rest-api/) for more information on this service.

n8n also provides:

- A [trigger node](../../trigger-nodes/n8n-nodes-base.venafitlsprotectcloudtrigger/) for Venafi TLS Protect Cloud.
- A [node](../n8n-nodes-base.venafitlsprotectdatacenter/) for Venafi TLS Protect Datacenter.

## What to do if your operation isn't supported

If this node doesn't support the operation you want to do, you can use the [HTTP Request node](../../core-nodes/n8n-nodes-base.httprequest/) to call the service's API.

You can use the credential you created for this service in the HTTP Request node:

1. In the HTTP Request node, select **Authentication** > **Predefined Credential Type**.
2. Select the service you want to connect to.
3. Select your credential.

Refer to [Custom API operations](../../../custom-operations/) for more information.
