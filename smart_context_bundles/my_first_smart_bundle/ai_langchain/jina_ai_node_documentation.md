# Jina AI node documentation

**Source:** https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.jinaai/

---

# Jina AI node

Use the Jina AI node to automate work in Jina AI and integrate Jina AI with other applications. n8n has built-in support for a wide range of Jina AI features.

Credentials

You can find authentication information for this node [here](../../credentials/jinaai/).

## Operations

- **Reader**:
  - **Read**: Fetches content from a URL and converts it to clean, LLM-friendly formats.
  - **Search**: Performs a web search using Jina AI and returns the top results as clean, LLM-friendly formats.
- **Research**:
  - **Deep Research**: Research a topic and generate a structured research report.

## Templates and examples

**AI Powered Web Scraping with Jina, Google Sheets and OpenAI : the EASY way**

by Derek Cheung

[View template details](https://n8n.io/workflows/2552-ai-powered-web-scraping-with-jina-google-sheets-and-openai-the-easy-way/)

**AI-Powered Information Monitoring with OpenAI, Google Sheets, Jina AI and Slack**

by Dataki

[View template details](https://n8n.io/workflows/2799-ai-powered-information-monitoring-with-openai-google-sheets-jina-ai-and-slack/)

**AI-Powered Research with Jina AI Deep Search**

by Leonard

[View template details](https://n8n.io/workflows/3068-ai-powered-research-with-jina-ai-deep-search/)

[Browse Jina AI integration templates](https://n8n.io/integrations/jina-ai/), or [search all templates](https://n8n.io/workflows/)

## Related resources

Refer to [Jina AI's reader API documentation](https://r.jina.ai/docs) and [Jina AI's search API documentation](https://s.jina.ai/docs) for more information about the service.

## What to do if your operation isn't supported

If this node doesn't support the operation you want to do, you can use the [HTTP Request node](../../core-nodes/n8n-nodes-base.httprequest/) to call the service's API.

You can use the credential you created for this service in the HTTP Request node:

1. In the HTTP Request node, select **Authentication** > **Predefined Credential Type**.
2. Select the service you want to connect to.
3. Select your credential.

Refer to [Custom API operations](../../../custom-operations/) for more information.
