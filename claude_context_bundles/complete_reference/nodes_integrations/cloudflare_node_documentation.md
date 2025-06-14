# Cloudflare node documentation

**Source:** https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.cloudflare/

---

# Cloudflare node

Use the Cloudflare node to automate work in Cloudflare, and integrate Cloudflare with other applications. n8n has built-in support for a wide range of Cloudflare features, including deleting, getting, and uploading zone certificates.

Credentials

Refer to [Cloudflare credentials](../../credentials/cloudflare/) for guidance on setting up authentication.

## Operations

- Zone Certificate
  - Delete
  - Get
  - Get Many
  - Upload

## Templates and examples

**Report phishing websites to Steam and CloudFlare**

by chaufnet

[View template details](https://n8n.io/workflows/122-report-phishing-websites-to-steam-and-cloudflare/)

**KV - Cloudflare Key-Value Database Full API Integration Workflow**

by Nskha

[View template details](https://n8n.io/workflows/2046-kv-cloudflare-key-value-database-full-api-integration-workflow/)

**Extract University Term Dates from Excel using CloudFlare Markdown Conversion**

by Jimleuk

[View template details](https://n8n.io/workflows/3505-extract-university-term-dates-from-excel-using-cloudflare-markdown-conversion/)

[Browse Cloudflare integration templates](https://n8n.io/integrations/cloudflare/), or [search all templates](https://n8n.io/workflows/)

## Related resources

Refer to [Cloudflare's API documentation on zone-level authentication](https://api.cloudflare.com/#zone-level-authenticated-origin-pulls-properties) for more information on this service.

## What to do if your operation isn't supported

If this node doesn't support the operation you want to do, you can use the [HTTP Request node](../../core-nodes/n8n-nodes-base.httprequest/) to call the service's API.

You can use the credential you created for this service in the HTTP Request node:

1. In the HTTP Request node, select **Authentication** > **Predefined Credential Type**.
2. Select the service you want to connect to.
3. Select your credential.

Refer to [Custom API operations](../../../custom-operations/) for more information.
