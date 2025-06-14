# SerpApi (Google Search) node documentation

**Source:** https://docs.n8n.io/integrations/builtin/cluster-nodes/sub-nodes/n8n-nodes-langchain.toolserpapi/

---

# SerpApi (Google Search) node

The SerpAPI node allows an [agent](../../../../../glossary/#ai-agent) in your workflow to call Google's Search API.

Credentials

You can find authentication information for this node [here](../../../credentials/serp/).

Parameter resolution in sub-nodes

Sub-nodes behave differently to other nodes when processing multiple items using an expression.

Most nodes, including root nodes, take any number of items as input, process these items, and output the results. You can use expressions to refer to input items, and the node resolves the expression for each item in turn. For example, given an input of five `name` values, the expression `{{ $json.name }}` resolves to each name in turn.

In sub-nodes, the expression always resolves to the first item. For example, given an input of five `name` values, the expression `{{ $json.name }}` always resolves to the first name.

## Node options

- **Country**: Enter the country code you'd like to use. Refer to [Google GL Parameter: Supported Google Countries](https://serpapi.com/google-countries) for supported countries and country codes.
- **Device**: Select the device to use to get the search results.
- **Explicit Array**: Choose whether to force SerpApi to fetch the Google results even if a cached version is already present (turned on) or not (turned off).
- **Google Domain**: Enter the Google Domain to use. Refer to [Supported Google Domains](https://serpapi.com/google-domains) for supported domains.
- **Language**: Enter the language code you'd like to use. Refer to [Google HL Parameter: Supported Google Languages](https://serpapi.com/google-languages) for supported languages and language codes.

## Templates and examples

**AI agent chat**

by n8n Team

[View template details](https://n8n.io/workflows/1954-ai-agent-chat/)

**✨🤖Automate Multi-Platform Social Media Content Creation with AI**

by Joseph LePage

[View template details](https://n8n.io/workflows/3066-automate-multi-platform-social-media-content-creation-with-ai/)

**AI chatbot that can search the web**

by n8n Team

[View template details](https://n8n.io/workflows/1959-ai-chatbot-that-can-search-the-web/)

[Browse SerpApi (Google Search) integration templates](https://n8n.io/integrations/serpapi/), or [search all templates](https://n8n.io/workflows/)

## Related resources

Refer to [Serp's documentation](https://serpapi.com/search-api) for more information about the service. You can also view [LangChain's documentation on their Serp integration](https://js.langchain.com/docs/integrations/tools/serpapi/).

View n8n's [Advanced AI](../../../../../advanced-ai/) documentation.

## AI glossary

- **completion**: Completions are the responses generated by a model like GPT.
- **hallucinations**: Hallucination in AI is when an LLM (large language model) mistakenly perceives patterns or objects that don't exist.
- **vector database**: A vector database stores mathematical representations of information. Use with embeddings and retrievers to create a database that your AI can access when answering questions.
- **vector store**: A vector store, or vector database, stores mathematical representations of information. Use with embeddings and retrievers to create a database that your AI can access when answering questions.
