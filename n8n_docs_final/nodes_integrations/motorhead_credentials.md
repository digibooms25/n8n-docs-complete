# Motorhead credentials

**Source:** https://docs.n8n.io/integrations/builtin/credentials/motorhead/

---

# Motorhead credentials

You can use these credentials to authenticate the following nodes:

- [Motorhead](../../cluster-nodes/sub-nodes/n8n-nodes-langchain.memorymotorhead/)

## Supported authentication methods

- API key

## Related resources

Refer to [Motorhead's API documentation](https://docs.getmetal.io/rest-api/introduction) for more information about the service.

View n8n's [Advanced AI](../../../../advanced-ai/) documentation.

## Using API key

To configure this credential, you'll need a [Motorhead](https://www.metal.ai/) account and:

- Your **Host** URL
- An **API Key**
- A **Client ID**

To set it up, you'll generate an API key:

1. If you're self-hosting Motorhead, update the **Host** URL to match your Motorhead URL.
2. In Motorhead, go to [**Settings > Organization**](https://app.getmetal.io/settings/organization).
3. In the **API Keys** section, select **Create**.
4. Enter a **Name** for your API Key, like `n8n integration`.
5. Select **Generate**.
6. Copy the **apiKey** and enter it in your n8n credential.
7. Return to the API key list.
8. Copy the **clientID** for the key and enter it as the **Client ID** in your n8n credential.

Refer to [Generate an API key](https://docs.getmetal.io/guides/misc-get-keys) for more information.
