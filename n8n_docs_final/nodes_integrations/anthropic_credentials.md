# Anthropic credentials

**Source:** https://docs.n8n.io/integrations/builtin/credentials/anthropic/

---

# Anthropic credentials

You can use these credentials to authenticate the following nodes:

- [Anthropic Chat Model](../../cluster-nodes/sub-nodes/n8n-nodes-langchain.lmchatanthropic/)

## Supported authentication methods

- API key

## Related resources

Refer to [Anthropic's documentation](https://docs.anthropic.com/claude/reference/getting-started-with-the-api) for more information about the service.

View n8n's [Advanced AI](../../../../advanced-ai/) documentation.

## Using API key

To configure this credential, you'll need an [Anthropic Console account](https://console.anthropic.com) with access to Claude.

Then:

1. In the Anthropic Console, open **Settings >** [**API Keys**](https://console.anthropic.com/settings/keys).
2. Select **+ Create Key**.
3. Give your key a **Name**, like `n8n-integration`.
4. Select **Copy Key** to copy the key.
5. Enter this as the **API Key** in your n8n credential.

Refer to Anthropic's [Intro to Claude](https://docs.anthropic.com/en/docs/intro-to-claude) and [Quickstart](https://docs.anthropic.com/en/docs/quickstart) for more information.
